<template>
  <section id="hero" class="relative min-h-screen flex items-center overflow-hidden">
    <!-- Background glows -->
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute top-1/4 -left-32 w-[500px] h-[500px] rounded-full bg-accent/10 blur-[120px]"></div>
      <div class="absolute bottom-1/4 -right-32 w-[400px] h-[400px] rounded-full bg-violet/10 blur-[120px]"></div>
    </div>
    <!-- Grid lines -->
    <div class="absolute inset-0 pointer-events-none" style="background-image: linear-gradient(rgba(79,142,247,0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(79,142,247,0.03) 1px, transparent 1px); background-size: 60px 60px;"></div>

    <div class="relative z-10 max-w-6xl mx-auto px-6 pt-28 pb-16 w-full">
      <div class="grid lg:grid-cols-2 gap-12 items-center">

        <!-- Left: text -->
        <div>
          <div class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full border border-border bg-surface/60 mb-8" style="animation: fadeUp 0.5s ease forwards;">
            <span class="w-2 h-2 rounded-full bg-red-500 animate-pulse"></span>
            <span class="text-xs font-display font-semibold tracking-widest uppercase text-slate-400">Not actively looking</span>
          </div>

          <h1 class="font-display font-extrabold leading-[1.1] text-5xl sm:text-6xl lg:text-7xl mb-6" style="animation: fadeUp 0.6s 0.1s ease both;">
            <span class="text-white">Daniel Paz</span><br />
            <span class="gradient-text">Rincón.</span>
          </h1>

          <p class="text-xl sm:text-2xl text-slate-400 font-light mb-4 leading-relaxed" style="animation: fadeUp 0.6s 0.2s ease both;">
            Software Developer &mdash; <span class="text-white font-medium">Backend</span> &amp; <span class="text-white font-medium">Mobile</span>,<br class="hidden sm:block" />
            specialized in <span class="text-accent font-medium">Java</span>, <span class="text-accent font-medium">Go</span> &amp; <span class="text-accent font-medium">iOS/Android</span>.
          </p>

          <p class="text-slate-500 max-w-xl text-base leading-relaxed mb-10" style="animation: fadeUp 0.6s 0.3s ease both;">
            Building efficient backend systems and cross-platform mobile apps.
            Currently at <span class="text-slate-300 font-medium">Minsait</span> in the Health sector,
            studying <span class="text-slate-300 font-medium">Cybersecurity Engineering</span> at UNIR.
          </p>

          <div class="flex flex-wrap gap-4 items-center" style="animation: fadeUp 0.6s 0.4s ease both;">
            <a href="#projects" @click.prevent="scrollTo('#projects')" class="btn-primary">
              See my work
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
            </a>
            <a href="#contact" @click.prevent="scrollTo('#contact')" class="btn-ghost">Get in touch</a>
          </div>

          <div class="flex gap-4 mt-10" style="animation: fadeUp 0.6s 0.5s ease both;">
            <a href="https://github.com/DanielParin" target="_blank" rel="noopener" class="social-link" aria-label="GitHub">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
            </a>
            <a href="mailto:dpazrincon@gmail.com" class="social-link" aria-label="Email">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
            </a>
            <a href="https://www.linkedin.com/in/daniel-paz-rincon" target="_blank" rel="noopener" class="social-link" aria-label="LinkedIn">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            </a>
          </div>
        </div>

        <!-- Right: photo -->
        <div class="hidden lg:flex justify-center items-center" style="animation: fadeIn 0.8s 0.3s ease both;">
          <div class="relative">
            <div class="absolute inset-0 rounded-2xl bg-accent/20 blur-3xl scale-90 -z-10"></div>
            <div class="relative rounded-2xl overflow-hidden border border-border/80 shadow-2xl" style="box-shadow: 0 0 60px rgba(79,142,247,0.12);">
              <img src="@/assets/Dani.png" alt="Daniel Paz Rincón" class="w-80 h-96 object-cover object-top" />
              <div class="absolute inset-x-0 bottom-0 h-24 bg-gradient-to-t from-dark/60 to-transparent"></div>
            </div>
            <div class="absolute -bottom-3 -right-3 w-6 h-6 rounded-full bg-accent"></div>
            <div class="absolute -top-3 -left-3 w-4 h-4 rounded-full border-2 border-accent/60"></div>
          </div>
        </div>

      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 opacity-40" style="animation: fadeIn 1s 1s ease both;">
      <span class="text-xs font-display tracking-widest text-slate-500 uppercase">Scroll</span>
      <div class="w-px h-10 bg-gradient-to-b from-slate-500 to-transparent"></div>
    </div>
  </section>
</template>

<script setup>
const scrollTo = (href) => {
  const el = document.querySelector(href)
  if (el) el.scrollIntoView({ behavior: 'smooth' })
}
</script>

<style scoped>
.social-link {
  display: flex; align-items: center; justify-content: center;
  width: 40px; height: 40px; border-radius: 10px;
  border: 1px solid #1c2333; color: #64748b; transition: all 0.2s ease;
}
.social-link:hover {
  border-color: #4f8ef7; color: #4f8ef7;
  background: rgba(79,142,247,0.08); transform: translateY(-2px);
}
</style>
