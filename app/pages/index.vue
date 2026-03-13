<template>
  <div class="min-h-screen bg-slate-50 font-sans">
    <!-- 导航栏 -->
    <nav class="bg-white shadow-sm sticky top-0 z-50">
      <div class="max-w-7xl mx-auto px-4 h-16 flex items-center justify-between">
        <div class="flex items-center gap-2">
          <div class="bg-emerald-600 p-1.5 rounded-lg">
            <Heart class="text-white w-6 h-6" />
          </div>
          <span class="text-xl font-bold text-slate-800 tracking-tight">云南省外出务工就业嘉兴服务站</span>
        </div>
        <div class="hidden md:flex gap-6 text-slate-600 font-medium">
          <a href="#" class="hover:text-emerald-600">服务项目</a>
          <a href="#" class="hover:text-emerald-600">申请流程</a>
          <a href="#" class="hover:text-emerald-600">关于我们</a>
        </div>
        <button class="bg-emerald-600 text-white px-5 py-2 rounded-full font-medium hover:bg-emerald-700 transition">
          立即求助
        </button>
      </div>
    </nav>

    <!-- 英雄区 (Hero Section) -->
    <header class="relative bg-emerald-700 py-16 md:py-24 overflow-hidden">
      <!-- 装饰背景 -->
      <div class="absolute inset-0 opacity-10">
        <svg class="w-full h-full" viewBox="0 0 100 100" preserveAspectRatio="none">
          <path d="M0 100 C 20 0 50 0 100 100 Z" fill="white"></path>
        </svg>
      </div>

      <div class="relative max-w-7xl mx-auto px-4 text-center">
        <span class="inline-block bg-emerald-500/30 text-emerald-50 text-sm px-4 py-1 rounded-full mb-4 border border-emerald-400/30">
          云南省外出务工人员公益服务项目
        </span>
        <h1 class="text-4xl md:text-6xl font-extrabold text-white mb-6 leading-tight">
          出省务工第一站 <br />
          <span class="text-yellow-400 underline decoration-wavy">岗前食宿全免费</span>
        </h1>
        <p class="text-emerald-50 text-lg md:text-xl max-w-2xl mx-auto mb-10 opacity-90">
          为每一位从云南出发、前往嘉兴等地的劳务工友提供温暖的落脚点。
          让您在拿到第一份工资前，吃饭不愁、住得安心。
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <button class="bg-yellow-400 text-emerald-900 px-8 py-4 rounded-xl text-xl font-bold shadow-lg hover:bg-yellow-300 transition-all flex items-center justify-center gap-2">
            <PhoneCall class="w-6 h-6" /> 我要求助
          </button>
          <button class="bg-white/10 backdrop-blur-md text-white border border-white/30 px-8 py-4 rounded-xl text-xl font-bold hover:bg-white/20 transition-all">
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
          <div class="w-12 h-12 bg-emerald-600 text-white rounded-full flex items-center justify-center text-xl font-bold mx-auto mb-4">
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

    <!-- 联系区 (Contact) -->
    <section class="bg-slate-900 text-white py-16">
      <div class="max-w-7xl mx-auto px-4 grid md:grid-cols-2 gap-12 items-center">
        <div>
          <h2 class="text-3xl font-bold mb-6">如果您正面临困难，<br/>请立即联系我们</h2>
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
            <input type="text" placeholder="您的姓名" class="w-full bg-white/10 border border-white/20 rounded-xl px-4 py-3 focus:outline-none focus:ring-2 focus:ring-emerald-500" />
            <input type="tel" placeholder="手机号码" class="w-full bg-white/10 border border-white/20 rounded-xl px-4 py-3 focus:outline-none focus:ring-2 focus:ring-emerald-500" />
            <textarea placeholder="简单描述您的情况（如：刚到嘉兴需要住宿）" rows="3" class="w-full bg-white/10 border border-white/20 rounded-xl px-4 py-3 focus:outline-none focus:ring-2 focus:ring-emerald-500"></textarea>
            <button class="w-full bg-emerald-600 py-4 rounded-xl font-bold text-lg hover:bg-emerald-500 transition shadow-lg shadow-emerald-900/20">
              提交申请，我们会主动联系您
            </button>
          </form>
        </div>
      </div>
    </section>

    <!-- 页脚 -->
    <footer class="bg-slate-950 text-slate-500 py-8 border-t border-white/5">
      <div class="max-w-7xl mx-auto px-4 text-center">
        <p>© 2024 滇籍劳务嘉兴关爱站 - 公益项目 · 非营利</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
// 引入图标
import { 
  Heart, PhoneCall, Home, UtensilsCrossed, 
  Briefcase, MapPin, Smartphone, ChevronRight 
} from 'lucide-vue-next';

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