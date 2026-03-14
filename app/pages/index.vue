<template>
  <div class="min-h-screen bg-slate-50 font-sans">


    <!-- 英雄区 (Hero Section) -->
    <header class="relative bg-emerald-700 py-16 md:py-24 overflow-hidden">
      <!-- 装饰背景 -->
      <div class="absolute inset-0 opacity-10">
        <svg class="w-full h-full" viewBox="0 0 100 100" preserveAspectRatio="none">
          <path d="M0 100 C 20 0 50 0 100 100 Z" fill="white"></path>
        </svg>
      </div>

      <div class="relative max-w-7xl mx-auto px-4 text-center">
        <span
          class="inline-block bg-emerald-500/30 text-emerald-50 text-sm px-4 py-1 rounded-full mb-4 border border-emerald-400/30">
          云南省外出务工人员公益服务项目
        </span>
        <h1 class="text-4xl md:text-6xl font-extrabold text-white mb-6 leading-tight">
          出省务工第一站 <br />
          <span class="text-yellow-400 underline decoration-wavy">岗前食宿全免费</span>
        </h1>
        <p class="text-emerald-50 text-lg md:text-xl max-w-2xl mx-auto mb-10 opacity-90">
          为每一位从云南出发、前往嘉兴的劳务工友提供温暖的落脚点。
          让您在拿到第一份工资前，吃饭不愁、住得安心。
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <a href="tel:13656617631"
            class="bg-yellow-400 text-emerald-900 px-8 py-4 rounded-xl text-xl font-bold shadow-lg hover:bg-yellow-300 transition-all flex items-center justify-center gap-2">
            <PhoneCall class="w-6 h-6" /> 我要求助
          </a>
          <button
            class="bg-white/10 backdrop-blur-md text-white border border-white/30 px-8 py-4 rounded-xl text-xl font-bold hover:bg-white/20 transition-all">
            了解政策
          </button>
        </div>
      </div>
    </header>

    <!-- 核心服务 (Core Services) -->
    <section class="max-w-7xl mx-auto px-4 -mt-10 relative z-10">
      <div class="grid md:grid-row-1 lg:grid-cols-3 gap-6">
        <!-- 免费住宿 -->
        <div class="bg-white p-8 rounded-2xl shadow-xl border-b-4 border-emerald-500">
          <div class="w-14 h-14 bg-emerald-100 rounded-full flex items-center justify-center mb-6">
            <Home class="text-emerald-600 w-8 h-8" />
          </div>
          <h3 class="text-2xl font-bold text-slate-800 mb-3">免费住宿</h3>
          <p class="text-slate-600 leading-relaxed text-lg">
            提供宿舍，配备干净净的床铺、热水淋浴及24小时安全值守。
          </p>
        </div>
        <!-- 免费餐食 -->
        <div class="bg-white p-8 rounded-2xl shadow-xl border-b-4 border-orange-500">
          <div class="w-14 h-14 bg-orange-100 rounded-full flex items-center justify-center mb-6">
            <UtensilsCrossed class="text-orange-600 w-8 h-8" />
          </div>
          <h3 class="text-2xl font-bold text-slate-800 mb-3">营养工作餐</h3>
          <p class="text-slate-600 leading-relaxed text-lg">
            餐食定时供应，符合云南口味，保证卫生健康，让您出门在外也有家乡味。
          </p>
        </div>
        <!-- 就业指导 -->
        <div class="bg-white p-8 rounded-2xl shadow-xl border-b-4 border-blue-500">
          <div class="w-14 h-14 bg-blue-100 rounded-full flex items-center justify-center mb-6">
            <Briefcase class="text-blue-600 w-8 h-8" />
          </div>
          <h3 class="text-2xl font-bold text-slate-800 mb-3">岗位对接</h3>
          <p class="text-slate-600 leading-relaxed text-lg">
            对接嘉兴本地优质企业，提供岗前培训和法律维权咨询，帮您找到靠谱工作。
          </p>
        </div>
      </div>
    </section>

    <!-- 流程说明 (Steps) -->
    <section class="py-20 max-w-7xl mx-auto px-4">
      <h2 class="text-3xl font-bold text-center text-slate-800 mb-16">如何申请免费食宿？</h2>
      <div class="grid md:grid-cols-4 gap-8">
        <div v-for="(step, index) in steps" :key="index" class="relative text-center">
          <div
            class="w-12 h-12 bg-emerald-600 text-white rounded-full flex items-center justify-center text-xl font-bold mx-auto mb-4">
            {{ index + 1 }}
          </div>
          <h4 class="font-bold text-lg mb-2">{{ step.title }}</h4>
          <p class="text-slate-500">{{ step.desc }}</p>
          <!-- 箭头装饰 (仅限桌面端) -->
          <div v-if="index < 3" class="hidden md:block absolute top-6 -right-4 text-emerald-200">
            <ChevronRight />
          </div>
        </div>
      </div>
    </section>
    <!-- 地图与导航模块 (Navigation Section) -->
    <!-- 到访指南 (Location & Navigation) -->
    <section class="py-24 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4">
        <!-- 标题区 -->
        <div class="text-center mb-16">
          <h2 class="text-3xl md:text-4xl font-bold text-slate-800 mb-4">如何找到我们？</h2>
          <p class="text-slate-500 max-w-2xl mx-auto">
            如果您已经抵达嘉兴，请参考以下信息前往关爱站。如果找不到路，请直接拨打我们的电话。
          </p>
        </div>

        <div class="grid lg:grid-cols-12 gap-8 items-stretch">
          <!-- 左侧：地图模拟窗 (视觉中心) -->
          <!-- 左侧：地图展示区 (带绿色滤镜与实景图) -->
          <div class="lg:col-span-7 relative group rounded-[2.5rem] overflow-hidden shadow-2xl border-8 border-white">

            <!-- 1. 底层地图图片 -->
            <!-- 建议：去高德地图截一张站点的图，替换下方的 src -->
            <img
              src="/img/ditu.png"
              alt="关爱站地图位置"
              class="w-full h-[500px] object-cover transition-transform duration-700 group-hover:scale-105" />

            <!-- 2. 核心：绿色滤镜层 (采用了 mix-blend-mode 叠加效果) -->
            <div class="absolute inset-0 bg-emerald-600/30 mix-blend-multiply pointer-events-none"></div>

            <!-- 3. 渐变遮罩层 (为了让顶部的文字和底部的按钮更清晰) -->
            <div class="absolute inset-0 bg-gradient-to-b from-black/20 via-transparent to-emerald-900/60"></div>

            <!-- 4. 装饰性：细微的网格扫描线 (增加科技感/专业感) -->
            <div class="absolute inset-0 opacity-20 pointer-events-none"
              style="background-image: radial-gradient(#fff 1px, transparent 1px); background-size: 20px 20px;">
            </div>

            <!-- 5. 浮动的地点标记 (带动画) -->
            <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 flex flex-col items-center">
              <!-- 呼吸灯光效 -->
              <div class="relative">
                <div class="absolute -inset-6 bg-white/40 rounded-full animate-ping"></div>
                <div class="absolute -inset-10 bg-emerald-400/20 rounded-full animate-pulse"></div>

                <!-- 定位图标 -->
                <div class="relative bg-white text-emerald-700 p-4 rounded-3xl shadow-2xl border-4 border-emerald-500">
                  <MapPin class="w-10 h-10 shadow-sm" strokeWidth="3" />
                </div>
              </div>

              <!-- 标签 -->
              <div class="mt-4 bg-white/90 backdrop-blur-md px-5 py-2 rounded-full shadow-lg border border-white">
                <span class="text-emerald-900 font-bold tracking-tight">您要找的服务站在这里</span>
              </div>
            </div>

            <!-- 6. 底部一键导航按钮 (常驻或悬浮) -->
            <div class="absolute bottom-6 left-6 right-6 flex gap-3">
              <a href="https://uri.amap.com/marker?position=120.72,30.66&name=滇籍劳务嘉兴服务站" target="_blank"
                class="flex-1 bg-white hover:bg-yellow-400 text-emerald-900 py-4 rounded-2xl font-bold shadow-xl transition-all flex items-center justify-center gap-2 group/btn">
                <Navigation class="w-5 h-5 text-emerald-600 group-hover/btn:scale-110 transition-transform" /> 高德导航
              </a>
              <a href="http://api.map.baidu.com/marker?location=30.745,120.760&title=滇籍劳务嘉兴关爱站&output=html"
                target="_blank"
                class="flex-1 bg-emerald-700/90 hover:bg-emerald-600 backdrop-blur-md text-white py-4 rounded-2xl font-bold shadow-xl transition-all flex items-center justify-center gap-2 border border-white/20">
                <MapIcon class="w-5 h-5 text-emerald-300" /> 百度导航
              </a>
            </div>
          </div>

          <!-- 右侧：文字详情与操作 -->
          <div class="lg:col-span-5 flex flex-col gap-6">
            <!-- 地址卡片 -->
            <div class="bg-emerald-700 text-white p-8 rounded-[2rem] shadow-lg relative overflow-hidden">
              <div class="relative z-10">
                <h3 class="text-emerald-200 text-sm font-bold uppercase tracking-wider mb-2">详细地址</h3>
                <p class="text-2xl font-bold mb-6 leading-snug">浙江省嘉兴市南湖区<br />嘉兴劳动大厦1楼</p>
                <button @click="copyAddress"
                  class="bg-emerald-500/30 hover:bg-emerald-500/50 border border-emerald-400/30 px-6 py-3 rounded-xl transition-all flex items-center gap-2 text-sm">
                  <Copy class="w-4 h-4" /> 复制地址到剪贴板
                </button>
              </div>
              <!-- 装饰图标 -->
              <MapPin class="absolute -right-4 -bottom-4 w-32 h-32 opacity-10 rotate-12" />
            </div>

            <!-- 交通指引卡片 -->
            <div class="bg-white p-8 rounded-[2rem] shadow-xl border border-slate-100 flex-1">
              <h3 class="text-slate-800 font-bold text-xl mb-6 flex items-center gap-2">
                <div class="w-1.5 h-6 bg-yellow-400 rounded-full"></div>
                乘车路线
              </h3>
              <div class="space-y-6">
                <div class="flex gap-4">
                  <div class="w-12 h-12 bg-orange-50 rounded-2xl flex-shrink-0 flex items-center justify-center">
                    <TrainFront class="w-6 h-6 text-orange-500" />
                  </div>
                  <div>
                    <p class="font-bold text-slate-700 text-lg">嘉兴火车站</p>
                    <p class="text-slate-500">下车后乘 <span class="text-emerald-600 font-medium">1路/10路</span> 公交直达</p>
                  </div>
                </div>
                <div class="flex gap-4">
                  <div class="w-12 h-12 bg-blue-50 rounded-2xl flex-shrink-0 flex items-center justify-center">
                    <Bus class="w-6 h-6 text-blue-500" />
                  </div>
                  <div>
                    <p class="font-bold text-slate-700 text-lg">嘉兴汽车南站</p>
                    <p class="text-slate-500">乘 <span class="text-emerald-600 font-medium">93路</span> 至XX路口下车</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 联系区 (Contact) -->
    <section class="bg-slate-900 text-white py-16">
      <div class="max-w-7xl mx-auto px-4 grid md:grid-cols-2 gap-12 items-center">
        <div>
          <h2 class="text-3xl font-bold mb-6">如果您正面临困难，<br />请立即联系我们</h2>
          <p class="text-slate-400 mb-8 text-lg">
            不管是刚下火车没地方去，还是找工作期间断了粮草，
            滇籍劳务关爱站永远是您的后盾。
          </p>
          <div class="space-y-4">
            <div class="flex items-center gap-4">
              <div class="bg-emerald-600/20 p-3 rounded-full">
                <MapPin class="text-emerald-500" />
              </div>
              <span>浙江省嘉兴市南湖区XX路XX号 (劳务关爱中心)</span>
            </div>
            <div class="flex items-center gap-4">
              <div class="bg-emerald-600/20 p-3 rounded-full">
                <Smartphone class="text-emerald-500" />
              </div>
              <span class="text-2xl font-mono">400-XXX-XXXX</span>
            </div>
          </div>
        </div>
        <div class="bg-white/5 p-8 rounded-3xl border border-white/10">
          <form @submit.prevent class="space-y-4">
            <input type="text" placeholder="您的姓名"
              class="w-full bg-white/10 border border-white/20 rounded-xl px-4 py-3 focus:outline-none focus:ring-2 focus:ring-emerald-500" />
            <input type="tel" placeholder="手机号码"
              class="w-full bg-white/10 border border-white/20 rounded-xl px-4 py-3 focus:outline-none focus:ring-2 focus:ring-emerald-500" />
            <textarea placeholder="简单描述您的情况（如：刚到嘉兴需要住宿）" rows="3"
              class="w-full bg-white/10 border border-white/20 rounded-xl px-4 py-3 focus:outline-none focus:ring-2 focus:ring-emerald-500"></textarea>
            <button
              class="w-full bg-emerald-600 py-4 rounded-xl font-bold text-lg hover:bg-emerald-500 transition shadow-lg shadow-emerald-900/20">
              提交申请，我们会主动联系您
            </button>
          </form>
        </div>
      </div>
    </section>


  </div>
</template>

<script setup>
// 引入图标
import {
  PhoneCall, Home, UtensilsCrossed, Briefcase,
  ChevronRight, MapPin, Smartphone,
  Navigation, Map as MapIcon, Copy, TrainFront, Bus
} from 'lucide-vue-next';
const copyAddress = () => {
  const address = "浙江省嘉兴市南湖区嘉兴劳动大厦1楼";
  navigator.clipboard.writeText(address);
  alert("地址已复制，可直接粘贴到地图软件查找");
};
// 流程步骤数据
const steps = [
  { title: '在线申请/拨打电话', desc: '通过网站或电话联系我们' },
  { title: '信息核实', desc: '出示有效身份证及务工证明' },
  { title: '拎包入住', desc: '抵达站点，入住免费宿舍' },
  { title: '安心找工作', desc: '享受食宿，对接企业面试' }
];

// Nuxt SEO 配置
useSeoMeta({
  title: '云南劳务关爱站 - 岗前免费食宿',
  description: '为云南省外出务工人员提供嘉兴岗前免费食宿服务。',
});
</script>

<style>
/* 可以在这里添加一些渐变动画 */
body {
  font-family: 'Inter', 'Noto Sans SC', sans-serif;
}
</style>