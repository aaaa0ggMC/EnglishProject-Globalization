<script setup>
import { computed, watch, onUnmounted } from 'vue'
import { useNav } from '@slidev/client'

const props = defineProps({
  text: {
    type: String,
    required: true
  },
  duration: {
    type: String,
    default: '2s'
  },
  fontSize: {
    type: String,
    default: '32px'
  },
  color: {
    type: String,
    default: 'white'
  },
  fontFamily: {
    type: String,
    default: 'ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace'
  },
  delay: {
    type: String,
    default: '0s'
  },
  showCursor: {
    type: Boolean,
    default: true
  },
  autoNext: {
    type: Boolean,
    default: false
  },
  thisPage: {
    type: Number,
    default: 1
  },
  // 动画完成后停留多久再跳转
  waitAfter: {
    type: String,
    default: '1s'
  }
})

const { next, currentPage } = useNav()
const length = computed(() => props.text.length)
const isActive = computed(() => currentPage.value === props.thisPage)

let timer = null

const startAutoNext = () => {
  if (!props.autoNext) return
  
  // 解析时间字符串为毫秒 (如 "2s" -> 2000)
  const parseTime = (t) => {
    const val = parseFloat(t)
    return t.endsWith('ms') ? val : val * 1000
  }

  const totalTime = parseTime(props.delay) + parseTime(props.duration) + parseTime(props.waitAfter)
  
  timer = setTimeout(() => {
    if (isActive.value) {
      next()
    }
  }, totalTime)
}

watch(isActive, (active) => {
  if (active) {
    startAutoNext()
  } else {
    if (timer) clearTimeout(timer)
  }
}, { immediate: true })

onUnmounted(() => {
  if (timer) clearTimeout(timer)
})
</script>

<template>
  <div class="typing-container">
    <!-- 使用 :key="isActive" 确保进入页面时重新触发 CSS 动画 -->
    <span 
      v-if="isActive"
      class="typing-content" 
      :class="{ 'no-cursor': !showCursor }"
      :style="{ 
        '--text-length': length,
        '--duration': duration,
        '--font-size': fontSize,
        '--color': color,
        '--font-family': fontFamily,
        '--delay': delay
      }"
    >
      {{ text }}
    </span>
  </div>
</template>

<style scoped>
.typing-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.typing-content {
  font-family: var(--font-family);
  display: inline-block;
  overflow: hidden;
  border-right: .15em solid var(--color);
  white-space: nowrap;
  letter-spacing: 0; 
  font-size: var(--font-size);
  color: var(--color);
  width: 0;
  animation: 
    typing var(--duration) steps(var(--text-length), end) forwards,
    blink-caret .75s step-end infinite;
  animation-delay: var(--delay);
}

.typing-content.no-cursor {
  border-right: none;
  animation: typing var(--duration) steps(var(--text-length), end) forwards;
  animation-delay: var(--delay);
}

@keyframes typing {
  from { width: 0 }
  to { width: calc(var(--text-length) * 1ch + 0.1ch) }
}

@keyframes blink-caret {
  from, to { border-color: transparent }
  50% { border-color: var(--color); }
}
</style>
