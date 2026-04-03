<script setup lang="ts">
import { ref, onUnmounted, watch, computed } from 'vue'
import { useNav } from '@slidev/client'

const imagesRecord = import.meta.glob('../pages/images/globalizations/*.png', { 
  eager: true, 
  import: 'default' 
})

const imageUrls = computed(() => {
  return Object.keys(imagesRecord)
    .sort((a, b) => {
      const getNum = (path: string) => parseInt(path.split('/').pop()?.split('.')[0] || '0')
      return getNum(a) - getNum(b)
    })
    .map(path => imagesRecord[path] as string)
})

interface Props {
  interval?: number
  duration?: number
  imageConfigs?: any[]
  autoNext?: boolean
  thisPage?: number // 告诉组件它在第几页
  blurAmount?: number
  blurRange?: string
  text?: string
  textPos?: { x: string, y: string }
  textSize?: string
}

const props = withDefaults(defineProps<Props>(), {
  interval: 100,
  duration: 6,
  imageConfigs: () => [],
  autoNext: true,
  thisPage: 2, // 默认设为 2
  blurAmount: 8,
  blurRange: "20% 80%",
  text: "",
  textPos: () => ({ x: '50%', y: '50%' }),
  textSize: '3.5rem'
})

const { next, currentPage } = useNav()
const currentIdx = ref(0)
let masterTimer: any = null

// 判断当前是否真的处于该页面
const isActive = computed(() => currentPage.value === props.thisPage)

const start = () => {
  if (masterTimer) clearInterval(masterTimer)
  
  // 重置状态
  currentIdx.value = 0
  let timeCount = 0
  const totalMs = props.duration * 1000

  // 唯一主计时器
  masterTimer = setInterval(() => {
    // 1. 切换图片
    currentIdx.value = (currentIdx.value + 1) % imageUrls.value.length
    
    // 2. 检测自动翻页
    timeCount += props.interval
    if (props.autoNext && timeCount >= totalMs) {
      clearInterval(masterTimer)
      next()
    }
  }, props.interval)
}

const stop = () => {
  if (masterTimer) {
    clearInterval(masterTimer)
    masterTimer = null
  }
}

// 极其关键：监控 Slidev 的当前页码
watch(isActive, (active) => {
  if (active) {
    // 只有进入这一页才启动
    start()
  } else {
    // 离开这一页立刻销毁
    stop()
  }
}, { immediate: true })

onUnmounted(() => stop())

const blurMask = computed(() => {
  const [start, end] = props.blurRange.split(' ')
  return `radial-gradient(circle, transparent ${start}, black ${end})`
})
</script>

<template>
  <div class="absolute inset-0 bg-black overflow-hidden pointer-events-none z-1">
    
    <!-- 1. 图片层 -->
    <div
      v-for="(url, i) in imageUrls"
      :key="url"
      class="absolute inset-0 flex items-center justify-center"
      :style="{ opacity: currentIdx === i ? 1 : 0, zIndex: currentIdx === i ? 2 : 1 }"
    >
      <img :src="url" class="w-full h-full object-cover" :style="{ transform: `scale(${props.imageConfigs[i]?.scale || 1}) translate(${props.imageConfigs[i]?.x || 0}%, ${props.imageConfigs[i]?.y || 0}%)` }" />
    </div>

    <!-- 2. 边缘模糊 -->
    <div class="absolute inset-0 z-5" :style="{ backdropFilter: `blur(${blurAmount}px)`, webkitBackdropFilter: `blur(${blurAmount}px)`, maskImage: blurMask, webkitMaskImage: blurMask }"></div>

    <!-- 3. 动画层：使用 :key="currentPage" 强制在翻页时重新渲染 DOM，重启 CSS 动画 -->
    <div v-if="isActive" :key="currentPage" class="absolute inset-0 z-50">
      <!-- 遮罩动画 (30/70/20) -->
      <div class="absolute inset-0 bg-black animate-bg-stage" :style="{ animationDuration: `${props.duration}s` }"></div>
      
      <!-- 文字动画 -->
      <div v-if="props.text" class="absolute z-100 font-bold uppercase tracking-widest text-white animate-text-stage" 
           :style="{ 
             left: props.textPos.x, 
             top: props.textPos.y, 
             fontSize: props.textSize, 
             animationDuration: `${props.duration}s`, 
             transform: 'translate(-50%, -50%)', 
             textShadow: '-3px -3px 0 #000, 3px -3px 0 #000, -3px 3px 0 #000, 3px 3px 0 #000' 
           }">
        {{ props.text }}
      </div>
    </div>

    <!-- 4. 边缘暗化层 -->
    <div class="absolute inset-0 z-60 vignette-overlay"></div>
  </div>
</template>

<style scoped>
/* 占比 30:70:20 总计 120 -> 25%, 83.3% */
@keyframes stageBgFade {
  0% { opacity: 1; }
  25% { opacity: 0; }
  83.3% { opacity: 0; }
  100% { opacity: 1; }
}

@keyframes stageTextFade {
  0% { opacity: 0; }
  25% { opacity: 1; }
  83.3% { opacity: 1; }
  100% { opacity: 0; }
}

.animate-bg-stage {
  animation: stageBgFade linear forwards;
}

.animate-text-stage {
  animation: stageTextFade linear forwards;
}

.vignette-overlay {
  background: radial-gradient(circle, transparent 20%, rgba(0, 0, 0, 0.4) 65%, rgba(0, 0, 0, 0.9) 100%);
}
</style>