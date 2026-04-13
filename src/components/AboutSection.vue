<template>
  <section id="about" class="py-28 relative">
    <div class="max-w-6xl mx-auto px-6">
      <div class="mb-16 reveal">
        <p class="section-tag mb-3">Who I am</p>
        <h2 class="font-display font-bold text-4xl sm:text-5xl text-white">About <span class="gradient-text">me</span></h2>
      </div>

      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <div class="space-y-6">
          <p class="text-slate-300 text-lg leading-relaxed reveal reveal-delay-1">
            I'm a software developer based in Spain with a strong focus on
            <span class="text-white font-medium">backend development</span> using
            <span class="text-accent font-medium">Java</span> and
            <span class="text-accent font-medium">Go</span>, and on
            <span class="text-white font-medium">mobile development</span> for iOS and Android.
            I enjoy building efficient, well-architected systems that actually solve problems.
          </p>
          <p class="text-slate-400 leading-relaxed reveal reveal-delay-2">
            I currently work at <span class="text-white font-medium">Minsait</span> as a FullStack Developer,
            implementing and maintaining features across multiple applications in the
            <span class="text-white font-medium">Health sector</span>, with a focus on mobile (iOS/Android)
            and backend with Java. Beyond my day job, I'm expanding my horizons studying a degree in
            <span class="text-white font-medium">Cybersecurity Engineering</span> at the
            <span class="text-white font-medium">Universidad Internacional de La Rioja (UNIR)</span>,
            which I started in January 2026.
          </p>
          <p class="text-slate-400 leading-relaxed reveal reveal-delay-3">
            I completed my studies in Cross-platform Software Development at
            <span class="text-white font-medium">IES Luis Vives</span> and I'm constantly looking to
            grow as an engineer — whether it's mastering new technologies, contributing to
            meaningful projects, or understanding systems at a deeper level.
          </p>
        </div>

        <div class="grid grid-cols-2 gap-4 reveal reveal-delay-2">
          <div v-for="stat in stats" :key="stat.label" class="glass rounded-2xl p-6 hover:border-accent/40 transition-colors duration-300">
            <p class="font-display font-bold text-4xl text-white mb-1">{{ stat.value }}</p>
            <p class="text-slate-500 text-sm font-medium">{{ stat.label }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const stats = [
  { value: '2+', label: 'Year of professional experience' },
  { value: '4+', label: 'Years coding & building projects' },
]
</script>
