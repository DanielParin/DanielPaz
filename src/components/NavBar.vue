<template>
  <header :class="['fixed top-0 inset-x-0 z-50 transition-all duration-300', scrolled ? 'py-3 bg-dark/80 backdrop-blur-xl border-b border-border/50' : 'py-5 bg-transparent']">
    <div class="max-w-6xl mx-auto px-6 flex items-center justify-between">
      <!-- Logo -->
      <a href="#hero" @click.prevent="scrollTo('#hero')" class="flex items-center">
        <img src="/logo.png" alt="DP Logo" class="h-9 w-9 object-contain" />
      </a>

      <!-- Desktop nav -->
      <nav class="hidden md:flex items-center gap-1">
        <a v-for="item in menu" :key="item.id" :href="item.href" @click.prevent="scrollTo(item.href)"
          :class="['px-4 py-2 rounded-lg text-sm font-medium font-display tracking-wide transition-all duration-200',
            activeSection === item.id ? 'text-accent bg-accent/10' : 'text-muted hover:text-white hover:bg-white/5']">
          {{ item.label }}
        </a>
        <a href="/DanielPaz/CV_DanielPaz.pdf" download class="ml-4 btn-primary text-sm !py-2 !px-5">
          <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>
          Resume
        </a>
      </nav>

      <!-- Mobile burger -->
      <button class="md:hidden text-white p-2" @click="isOpen = !isOpen" aria-label="Toggle menu">
        <div class="w-6 flex flex-col gap-1.5">
          <span :class="['block h-0.5 bg-white transition-all duration-300', isOpen ? 'rotate-45 translate-y-2' : '']"></span>
          <span :class="['block h-0.5 bg-white transition-all duration-300', isOpen ? 'opacity-0' : '']"></span>
          <span :class="['block h-0.5 bg-white transition-all duration-300', isOpen ? '-rotate-45 -translate-y-2' : '']"></span>
        </div>
      </button>
    </div>

    <!-- Mobile menu -->
    <Transition name="slide-down">
      <nav v-if="isOpen" class="md:hidden bg-dark/95 backdrop-blur-xl border-t border-border/50 px-6 py-6 flex flex-col gap-2">
        <a v-for="item in menu" :key="item.id" :href="item.href"
          @click.prevent="scrollTo(item.href); isOpen = false"
          :class="['px-4 py-3 rounded-lg font-display font-medium tracking-wide text-base transition-all',
            activeSection === item.id ? 'text-accent bg-accent/10' : 'text-slate-300']">
          {{ item.label }}
        </a>
        <a href="/DanielPaz/CV_DanielPaz.pdf" download class="mt-2 btn-primary justify-center">Download Resume</a>
      </nav>
    </Transition>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
defineProps({ activeSection: String })

const scrolled = ref(false)
const isOpen = ref(false)
const menu = [
  { id: 'about', label: 'About', href: '#about' },
  { id: 'experience', label: 'Experience', href: '#experience' },
  { id: 'skills', label: 'Skills', href: '#skills' },
  { id: 'projects', label: 'Projects', href: '#projects' },
  { id: 'contact', label: 'Contact', href: '#contact' },
]
const scrollTo = (href) => {
  const el = document.querySelector(href)
  if (el) el.scrollIntoView({ behavior: 'smooth' })
}
const onScroll = () => { scrolled.value = window.scrollY > 40 }
onMounted(() => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<style scoped>
.text-muted { color: #64748b; }
.bg-dark\/80 { background-color: rgba(7,9,15,0.8); }
.bg-dark\/95 { background-color: rgba(7,9,15,0.95); }
.slide-down-enter-active, .slide-down-leave-active { transition: all 0.25s ease; }
.slide-down-enter-from, .slide-down-leave-to { opacity: 0; transform: translateY(-8px); }
</style>
