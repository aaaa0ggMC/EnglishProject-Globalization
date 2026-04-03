---
layout: center
class: bg-white text-black
---
# Topic: Chinese Culture or Globalization(Local customs,The issue of globalization...)

Presented by Group1

<div class="absolute bottom-10 left-0 right-0 text-center">
  <a 
    href="https://aaaa0ggmc.github.io/EnglishProject-Globalization" 
    target="_blank" 
    style="text-decoration: none; color: inherit; opacity: 0.6; font-size: 14px;"
    onmouseover="this.style.opacity='1'"
    onmouseout="this.style.opacity='0.6'"
  >
    aaaa0ggmc.github.io/EnglishProject-Globalization
  </a>
</div>

---
layout: center
transition: fade
class: bg-black text-white
---

<TypingText 
  text="In the inevitable process of" 
  :autoNext="true" 
  :thisPage="2" 
  waitAfter="0.2s"
  :showCursor="false"  
  fontSize="48px"
  duration="3s"
/>

---
layout: center
class: text-white p-0
---

<GlobalizationsBackground 
  :thisPage="3"
  :interval="100"
  :duration="4"
  :autoNext="true"
  :imageConfigs="[
    { scale: 1.8, x: -0.5, y: -10 },
    { scale: 1.9, x: 6, y: 6 },
    { scale: 1.5, x: 3, y: 0 },
    { scale: 1.7, x: -3, y: 18 },
    { scale: 2.2, x: -11, y: 0 },
    { scale: 1.2, x: -10, y: 30 },
    { scale: 2, x: -1.45, y: 22 },
    { scale: 2, x: -6, y: 20 },
    { scale: 1.9, x: 13, y: 33 },
    { scale: 2.1, x: 13, y: 33 },
  ]"
  :blurAmount="16"
  :blurRange="'10% 80%'"
/>

---
layout: center
transition: fade
class: bg-black text-white
---

<TypingText 
  :thisPage="4"
  text="What will be the fate of " 
  :showCursor="false"  
  fontSize="32px"
  duration="1.2s"
  color="#cccccc"
/>
<TypingText 
  :thisPage="4"
  text="Our Cultures?" 
  :showCursor="false"  
  delay="1.1s"
  fontSize="64px"
  duration="1s"
  color="#ff4444"
/>

---
layout: default
class: text-white
transition: view-transition
---

<style scoped>
.slidev-layout {
  background-image: url('/images/stone2.png') !important;
  background-size: 130%;
  background-position: center;
  background-position: 47% 19%;
}

.globalization-text {
  view-transition-name: globalization-word;
  /* 可选：让它在离开时有平滑效果 */
  transition: all 0.6s ease;
}
</style>

<div style="
    position: absolute; 
    left: 50%; 
    top: 40%; 
    transform: translate(-50%, -50%); 
    font-size: 40px; 
    white-space: nowrap;
    font-family: sans-serif;
"> 
    <span
      class="globalization-text"
      style="
      font-size: 32px;
      color: #aaaaaa;
      font-style: italic;
    ">Floating on the tide of globalization</span>
    <br>
    One Must Imagine Our 
    <span style="color: #ff4444; font-weight: bold;">Cultures</span> 
    Thriving
</div>

---
layout: default
transition: view-transition
class: text-white
---
<style scoped>
.globalization-text {
  view-transition-name: globalization-word;
}

.cultures-text {
  view-transition-name: cultures;
}

.slidev-layout {
  background-image: url('/images/earth-blur.jpg') !important;
  background-size: 120% no-repeat;
  background-position: center;
  background-position: 48% -15%;
}
</style>
<h1 class="text-center globalization-text"
style="
  font-size: 42px;
"
>
  Why <span class="">Globalization</span> Is Inevitable
</h1>


<div v-click="[2,4]" 
style="
  position: absolute;
  left : -6%;
  top : 10%;
  font-size: 32px;
  transform: scale(0.6);
"
>
<span>China's Busy Ports</span>
<img class="rounded-xl" src="/images/china_ports.webp"></img>
</div>

<div v-click="[3,4]" 
style="
  position: absolute;
  left : 50%;
  top : 28%;
  font-size: 24px;
"
>
<span>The Hub of Global Manufacturing</span>
<img class="rounded-xl" src="/images/made_in_cn.jpg"></img>
</div>


<div v-click="[5,7]" 
style="
  position: absolute;
  left : -2%;
  top : 15%;
  font-size: 36px;
  transform: scale(0.6);
"
>
<span>Isolation: The Opium Wars</span>
<img class="rounded-xl" src="/images/war_of_drugs.jpeg"></img>
</div>

<div v-click="[6,7]" 
style="
  position: absolute;
  left : 32%;
  top : 18%;
  font-size: 36px;
  z-index: 1;
  transform: scale(0.7);
"
>
<span>Openness: Modern Prosperity</span>
<img class="rounded-xl" src="/images/today.jpeg"></img>
</div>

<div
  style="
    font-size: 32px;
    position: absolute; 
    left: 10%; 
    top: 16%; 
  "
>
<p v-click="1"><span style="
  color: gray;
">1.</span>The frequent material and cultural changes</p>
<p v-click="4"><span style="
  color: gray;
">2.</span>The historical lesson: Isolation leads to vulnerability</p>
</div>


<div
  style="
    white-space: nowrap;
    font-size: 36px;
    position: absolute; 
    left: 50%; 
    top: 60%; 
    transform: translate(-50%, 0);
  "
>

<p v-click="7" style="
  text-align: center;
">Our country keeps advancing to fit globalization,</p>
<p class="cultures-text" v-click="8" style="
  text-align: center;
">so do our cultures.</p>
</div>


---
transition: view-transition
class: bg-[#0a0a0a] text-white
---

<style scoped>
.cultures-text {
  view-transition-name: cultures;
  background: linear-gradient(to bottom, #cccccc, #dddddd);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.fusions-text {
  view-transition-name: fusions;
}

.pop-in {
  animation: pop-in 0.8s cubic-bezier(0.16, 1, 0.3, 1) both;
}

@keyframes pop-in {
  0% { opacity: 0; transform: translateY(20px) scale(0.9); }
  100% { opacity: 1; transform: translateY(0) scale(1); }
}

.delay-1 { animation-delay: 0.6s; }
.delay-2 { animation-delay: 1.0s; }
</style>

<div class="h-full flex flex-col items-center justify-center">
  
  <h1 class="cultures-text text-7xl font-bold mb-16 tracking-tighter">
    The Shift Of Our Cultures
  </h1>

  <div class="flex gap-24 text-4xl font-extralight tracking-[0.2em] uppercase">
    <div class="pop-in delay-1 flex flex-col items-center">
      <div class="h-[2px] w-12 bg-[#d4a373] mb-4 fusions-text"></div>
      <span class="opacity-90">Fusion</span>
    </div>
    <div class="pop-in delay-2 flex flex-col items-center">
      <div class="h-[2px] w-12 bg-[#457b9d] mb-4"></div>
      <span class="opacity-90">Record</span>
    </div>
  </div>
</div>

---
transition: view-transition
class: bg-[#0a0a0a] text-white
---
<style scoped>
.fusions-text {
  view-transition-name: fusions;
}
</style>

<div v-click="[3,6]" 
style="
  position: absolute;
  left : -15%;
  top : 10%;
">
<div style="transform: scale(0.5);">
<span style="font-size: 48px;">Black Myth Wukong</span>
<img class="rounded-xl" src="/images/xqc_black_myth.png"></img>
</div>
</div>

<div v-click="[4,6]" 
style="
  position: absolute;
  left : 20%;
  top : 5%;
">
<div style="transform: scale(0.5);">
<span style="font-size: 48px;">Animes made in China</span>
<img class="rounded-xl" src="/images/animes.png"></img>
</div>
</div>


<div v-click="[5,6]" 
style="
  position: absolute;
  left : 60%;
  top : 5%;
">
<div style="transform: scale(0.5);">
<span style="font-size: 48px;">Novels</span>
<img class="rounded-xl" src="/images/ten_days.jpg"></img>
</div>
</div>

# <span class='text-orange fusions-text'>Fusions</span>

<div v-click="1" class="absolute inset-0 p-12 flex flex-col"
  style="
    transform : scale(0.8);
  "
>

  <h2 class="text-3xl font-bold mb-4">
    <span class='text-gray'>1.</span> "Frieren" Sings Peking Opera 
  </h2>

  <div class="flex-grow w-full">
    <iframe 
      v-if="$clicks === 1"
      src="//player.bilibili.com/player.html?bvid=BV1XWFpzNEcm&cid=339262048&page=1&high_quality=1&danmaku=0&autoplay=false" 
      class="w-full h-full rounded-lg shadow-lg"
      allowfullscreen="allowfullscreen" 
      scrolling="no" 
      frameborder="0" 
      sandbox="allow-top-navigation allow-same-origin allow-forms allow-scripts"
    ></iframe>
  </div>
  
</div>

<div v-click="2" class="absolute inset-0 p-12 flex flex-col"
  style="
    transform: scale(0.8);
    top : 10%
  "
>
  <h2 class="text-3xl font-bold mb-4">
    <span class='text-gray'>2.</span> E-products that Combines Chinese Culture with Western(mainly) techniques / elements
  </h2>  
</div>

---
class: bg-[#0a0a0a] text-white
transition: view-transition
---
<style scoped>
.person-text {
  view-transition-name: persons;
}
</style>
# <span class='text-blue'>Records</span>
<div class="person-text">

## NanXiang

<div
style="
  position: absolute;
  left : 10%;
  top : 6%;
  font-size: 32px;
  transform: scale(0.5);
"
>
<img class="rounded-xl" src="/images/nanxiang.png"></img>
</div>

</div>

<div v-click="1"
style="
  position: absolute;
  left : -20%;
  top : 0%;
  font-size: 42px;
  transform: scale(0.5);
"
>
<span>Fire Tigers in Zou Town(邹城火虎)</span>
<img class="rounded-xl" src="/images/nanxiang_fire.png"></img>
</div>

<div v-click="2"
style="
  position: absolute;
  left : 40%;
  top : 23%;
  font-size: 28px;
  transform: scale(0.9);
"
>
<span>Zhongyuan Festival</span>
<img class="rounded-xl" src="/images/reminisce.png"></img>
</div>

---
class: bg-[#0a0a0a] text-white
transition: view-transition
---
<style scoped>
.person-text {
  view-transition-name: persons;
}
</style>


# <span class='text-blue'>Records</span>

<div class="person-text">

## ShanBai The Returner
<div
style="
  position: absolute;
  left : 20%;
  top : 5%;
  font-size: 32px;
  transform: scale(0.4);
"
>
<img class="rounded-xl" src="/images/guy_town.png"></img>
</div>
</div>

<div v-click="1"
style="
  position: absolute;
  left : -10%;
  top : -30%;
  font-size: 60px;
  transform: scale(0.4);
"
>
<span>JunChina(钧瓷)</span>
<img class="rounded-xl" src="/images/c_1.png"></img>
</div>

<div v-click="2"
style="
  position: absolute;
  left : 70%;
  top : 10%;
  font-size: 32px;
  transform: scale(1);
"
>
<span>Pipa</span>
<img class="rounded-xl" src="/images/pipa.png"></img>
</div>


---
class: bg-[#0a0a0a] text-white
---
# <span class='obstacles text-green'>Pros.</span>

<div v-click="1">

## <span class='text-gray'>1. </span> <span class='text-cyan'>The Revitalization of Traditional Cultures</span>

</div>

<div v-click="1"
  style="
    font-size: 26px;
  "
>
&emsp;&emsp;These shifts have successfully breathed new life into traditions for a global audience. By integrating modern techniques and elements, our heritage has become significantly more engaging and accessible.
</div>

<div v-click="2">

## <span class='text-gray'>2. </span> <span class='text-cyan'>The Digital Ambers(电子琥珀) of Traditions</span>

</div>

<div v-click="2"
  style="
    font-size: 27px;
  "
>
&emsp;&emsp;Records capture and freeze time, crystallizing significant cultural milestones that might otherwise fade away. By transforming ephemeral traditions into "Digital Ambers," we safeguard our heritage against modernization, ensuring future generations can still resonate with their ancestral roots in this changing world.
</div>

---
class: bg-[#0a0a0a] text-white
layout: center
transition: view-transition
---

<div class="obstacles">
<TypingText 
  text="But where there is change, there are obstacles." 
  :autoNext="false" 
  :thisPage="12" 
  waitAfter="0.2s"
  :showCursor="false"  
  fontSize="32px"
  duration="2s"
/>
</div>

---
class: bg-[#0a0a0a] text-white
---

# <span class='text-cyan'>Cons.</span>

<div v-click="1">

## <span class='text-gray'>1. </span> <span class='text-cyan'>The Erosion Of Original Meaning</span>

</div>

<div v-click="1"
  style="
    font-size: 28px;
  "
>
&emsp;&emsp;The adaptation of authentic traditions may simplify their original stories, trading deep cultural meanings for more likes and views.
</div>

<div v-click="2">

## <span class='text-gray'>2. </span> <span class='text-cyan'>The Over-spilled Attributes of Entertainment for Some Customs</span>

</div>

<div v-click="2"
  style="
    font-size: 28px;
  "
>
&emsp;&emsp;Serious rituals often turn into mere spectacles, where the fun of entertainment completely overshadows the true spirit of the tradition.
</div>

<div v-click="3">

## <span class='text-gray'>3. </span> <span class='text-cyan'>The Critism of Being Meaningless/Wasteful etc.</span>
</div>

---
class: bg-[#0a0a0a]  text-white
transition: view-transition
---
# <span class='text-red'>Examples</span>

<div v-click
 style="
  position: absolute;
  transform: translate(-50%,-50%);
  scale : 0.5;
  border: 6px solid orange;
  border-radius: 1rem;
">
<img class="rounded-xl" src="/critism/0.png"></img>
</div>

<div v-click 
style="
  position: absolute;
  transform: translate(0%,0%);
  scale : 0.6;
  left: -10%;
  top : 0%;
  border: 6px solid orange;
  border-radius: 1rem;
">
<img class="rounded-xl" src="/critism/1.png"></img>
</div>

<div v-click 
style="
  position: absolute;
  transform: translate(0%,0%);
  scale : 0.6;
  left: -5%;
  top : 3%;
  border: 6px solid orange;
  border-radius: 1rem;
">
<img class="rounded-xl" src="/critism/2.png"></img>
</div>

<div v-click 
style="
  position: absolute;
  transform: translate(0%,0%);
  scale : 0.7;
  left: 10%;
  top : 10%;
  border: 6px solid orange;
  border-radius: 1rem;
">
<img class="rounded-xl" src="/critism/3.png"></img>
</div>

<div v-click>

<div
style="
  position: absolute;
  transform: translate(0%,0%);
  scale : 0.25;
  left: -19%;
  top : -110%;
  border: 6px solid orange;
  border-radius: 1rem;
">
<img class="rounded-xl" src="/critism/nvs.jpg"></img>
</div>


<div
style="
  position: absolute;
  color: black;
  background-color: #ffffff;
  font-size: 24px;
  left: 50%;
  top : 9.7%;
  width: 48%;
  padding: 1.5rem;
  border: 6px solid orange;
  border-radius: 1rem;
"
>
  <span class="font-bold text-orange-600 text-2xl">Echoes of an Ancient Critique</span>
  <div class="mt-4 leading-relaxed">
    <p>
      Modern web novels often fall into the same trap observed by <strong>Cao Xueqin</strong> centuries ago: 
    </p>
    <p class="italic text-gray-700 mt-2">
      "Thousands of stories sharing one tone; thousands of characters sharing one face."
    </p>
    <p class="mt-4 text-lg">
      This <strong>"cloned narrative"</strong>—repetitive tropes and shallow archetypes—remains a persistent challenge in our digital cultural shift.
    </p>
  </div>
  
  <p class="mt-6 text-sm text-gray-500 border-t pt-2">
    <strong>Note:</strong> This critique targets generic industry patterns, not the specific quality of individual works. 
  </p>
</div>

</div>

---
class: bg-[#0a0a0a]  text-white
---
# <span class='text-red'>Examples</span>

<div
  style="
    position: absolute;
    transform: translate(-50%,0%);
    white-space: nowrap;
    left : 50%;
    top: 40%;
    font-size: 32px;
  "
>

<p>Are these shifts just a <span class='text-gray'>digital tomb</span> instead of a <span class="text-orange">digital amber</span>?</p>

<p class="text-cyan" v-click>There is no definitive answer, only an ongoing struggle.</p>
</div>

---
layout: center
class: bg-[#0a0a0a]  text-white
---
# However, that's why our <span class='text-red'>cultures</span> keep advancing.

---
layout: default
class: bg-[#0a0a0a] text-white
---

# <span class='text-blue'>Evidence</span> from Other Fields

<div class="grid grid-cols-2 gap-10 mt-12">

  <div v-click="1" class="border-l-2 border-blue-500 pl-6">
    <h2 class="text-4xl mb-4 font-bold text-blue-400">Mathematics</h2>
    <p class="text-xl leading-relaxed">
      In the past, people doubted <b>"Negative Numbers"</b> and <b>"Zero"</b>. They thought these were "meaningless".
    </p>
    <p class="mt-4 text-gray-400 italic">
      But today, they are the foundation of our <b>Digital World</b> and AI.
    </p>
  </div>

  <div v-click="2" class="border-l-2 border-orange-500 pl-6">
    <h2 class="text-4xl mb-4 font-bold text-orange-400">Physics</h2>
    <p class="text-xl leading-relaxed">
      When <b>Quantum Physics</b> first appeared, it challenged all old rules. Scientists argued for decades.
    </p>
    <p class="mt-4 text-gray-400 italic">
      But this "conflict" led to <b>Computers</b>, <b>Lasers</b>, and our modern life.
    </p>
  </div>

</div>

<div v-click="3" class="mt-20 text-center">
  <div class="h-[1px] w-full bg-gray-800 mb-8"></div>
  <p class="text-2xl tracking-wide">
    History proves that <span class="text-red-500 font-bold underline">Conflict</span> is the real fuel of <span class="text-green-500 font-bold underline">Progress</span>.
  </p>
</div>

---
layout: default
class: text-white
transition: view-transition
---
<style scoped>
.slidev-layout {
  background-image: url('/images/stone2.png') !important;
  background-size: 130%;
  background-position: center;
  background-position: 47% 19%;
}
</style>

<div style="
    position: absolute; 
    left: 50%; 
    top: 40%; 
    transform: translate(-50%, -50%); 
    font-size: 40px; 
    white-space: nowrap;
    font-family: sans-serif;
"> 
    <span
      class="globalization-text"
      style="
      font-size: 32px;
      color: #aaaaaa;
      font-style: italic;
    ">Although not perfect</span>
    <br>
    One Must Imagine Our 
    <span style="color: #ff4444; font-weight: bold;">Cultures</span> 
    Thriving
</div>

---
layout: center
class: bg-[#0a0a0a] text-white
---
# Thanks
Slide Design & Script: Rock <br/>
Presenter: WZR <br/>
Narrative: ZSD <br/>
Technical Support: CGT HQF 


---
class: bg-[#0a0a0a] text-white
---
# <span class='text-cyan'>Appendix</span>
## <span class='text-gray'>Original Text From <italic>Dream of the Red Chamber</italic></span>
&emsp;&emsp;至若佳人才子等书，则又千部共出一套，且其中终不能不涉于淫滥，以致满纸潘安、子建、西子、文君、不过作者要写出自己的那两首情诗艳赋来，故假拟出男女二人名姓，又必旁出一小人其间拨乱，亦如剧中之小丑然。
