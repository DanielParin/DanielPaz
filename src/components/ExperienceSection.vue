<template>
  <section id="experience" class="py-28 relative">
    <div class="absolute right-0 top-0 w-[400px] h-[400px] rounded-full bg-violet/5 blur-[100px] pointer-events-none"></div>

    <div class="max-w-6xl mx-auto px-6">
      <div class="mb-16 reveal">
        <p class="section-tag mb-3">Background</p>
        <h2 class="font-display font-bold text-4xl sm:text-5xl text-white">Experience &<br /><span class="gradient-text">Education</span></h2>
      </div>

      <div class="grid lg:grid-cols-2 gap-12 lg:gap-20">
        <!-- Experience -->
        <div>
          <h3 class="font-display font-semibold text-lg text-slate-400 uppercase tracking-widest mb-8 reveal">Work Experience</h3>
          <div class="space-y-6">
            <div v-for="(item, i) in experience" :key="item.id" :class="['reveal', `reveal-delay-${i + 1}`]">
              <div class="relative pl-6 border-l border-border">
                <div class="absolute -left-[5px] top-1.5 w-2.5 h-2.5 rounded-full bg-accent ring-4 ring-dark"></div>
                <div class="glass rounded-xl p-5 hover:border-accent/40 transition-colors duration-300 ml-4">
                  <div class="flex items-start justify-between gap-3 flex-wrap mb-2">
                    <h4 class="font-display font-bold text-white text-lg">{{ item.role }}</h4>
                    <span class="text-xs px-2 py-1 rounded-full border border-accent/30 text-accent font-medium whitespace-nowrap">{{ item.type }}</span>
                  </div>
                  <p class="text-accent font-semibold text-sm mb-1">{{ item.company }}</p>
                  <p class="text-slate-500 text-xs mb-3">{{ item.date }}</p>
                  <p class="text-slate-400 text-sm leading-relaxed">{{ item.description }}</p>
                  <div class="flex flex-wrap gap-2 mt-3">
                    <span v-for="t in item.stack" :key="t" class="text-xs px-2.5 py-1 rounded-full bg-surface border border-border text-slate-400">{{ t }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Education -->
        <div>
          <h3 class="font-display font-semibold text-lg text-slate-400 uppercase tracking-widest mb-8 reveal">Education</h3>
          <div class="space-y-6">
            <div v-for="(item, i) in education" :key="item.id" :class="['reveal', `reveal-delay-${i + 1}`]">
              <div class="relative pl-6 border-l border-border">
                <div class="absolute -left-[5px] top-1.5 w-2.5 h-2.5 rounded-full bg-violet ring-4 ring-dark"></div>
                <div class="glass rounded-xl p-5 hover:border-violet/40 transition-colors duration-300 ml-4">
                  <h4 class="font-display font-bold text-white text-lg mb-1">{{ item.school }}</h4>
                  <p class="text-violet font-semibold text-sm mb-1">{{ item.degree }}</p>
                  <p class="text-slate-500 text-xs mb-3">{{ item.year }}</p>
                  <p class="text-slate-400 text-sm leading-relaxed">{{ item.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const experience = [
  {
    id: 1,
    role: 'FullStack Developer',
    company: 'Minsait',
    date: 'November 2025 – Present',
    type: 'Full-time',
    description: 'Implementing and maintaining features across multiple applications in the Health sector. Focus on mobile development for iOS and Android, and backend services with Java.',
    stack: ['Java', 'Swift', 'Kotlin', 'Spring', 'SQL', 'Git'],
  },
  {
    id: 2,
    role: 'FullStack Developer',
    company: 'NEORIS',
    date: 'September 2024 – November 2025',
    type: 'Full-time',
    description: 'Worked as part of a professional development team building and maintaining enterprise-grade applications, contributing to both backend services and frontend interfaces.',
    stack: ['Java', 'Spring', 'Vue', 'Angular', 'SQL', 'Git'],
  },
]

const education = [
  {
    id: 1,
    school: 'Universidad Internacional de La Rioja (UNIR)',
    degree: 'Engineering Degree in Cybersecurity',
    year: 'January 2026 – Present',
    description: 'Currently pursuing a full engineering degree focused on cybersecurity, network security, cryptography, and secure software development.',
  },
  {
    id: 2,
    school: 'IES Luis Vives',
    degree: 'Higher Technician — Cross-platform Software Development',
    year: '2022 – 2024',
    description: 'Focused on software development across platforms including web, desktop, and mobile. Covered Java, databases, web technologies, and agile workflows.',
  },
]
</script>
