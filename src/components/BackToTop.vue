<template>
  <Transition name="fade">
    <button
      v-if="visible"
      @click="scrollTop"
      class="fixed bottom-8 right-8 z-50 w-11 h-11 rounded-xl border border-border bg-surface/80 backdrop-blur-sm text-slate-400 flex items-center justify-center hover:border-accent hover:text-accent hover:-translate-y-1 transition-all duration-200 shadow-lg"
      aria-label="Back to top"
    >
      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="18 15 12 9 6 15"/>
      </svg>
    </button>
  </Transition>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const visible = ref(false)
const onScroll = () => { visible.value = window.scrollY > 400 }
const scrollTop = () => window.scrollTo({ top: 0, behavior: 'smooth' })

onMounted(() => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<style scoped>
.fade-enter-active, .fade-leave-active { transition: opacity 0.3s, transform 0.3s; }
.fade-enter-from, .fade-leave-to { opacity: 0; transform: translateY(8px); }
</style>
