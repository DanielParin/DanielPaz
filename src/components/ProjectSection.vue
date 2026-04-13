<template>
  <section id="projects" class="py-28 relative">
    <div class="absolute right-0 top-1/2 w-[350px] h-[350px] rounded-full bg-violet/5 blur-[80px] pointer-events-none"></div>

    <div class="max-w-6xl mx-auto px-6">
      <!-- Section header -->
      <div class="mb-16 reveal">
        <p class="section-tag mb-3">What I've built</p>
        <h2 class="font-display font-bold text-4xl sm:text-5xl text-white">My <span class="gradient-text">Projects</span></h2>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <article
          v-for="(project, i) in projects"
          :key="project.id"
          :class="['group glass rounded-2xl overflow-hidden hover:border-accent/40 hover:-translate-y-1 transition-all duration-300 reveal', `reveal-delay-${i + 1}`]"
        >
          <!-- Image area -->
          <div class="relative h-48 overflow-hidden bg-surface">
            <img
              v-if="project.image"
              :src="project.image"
              :alt="project.title"
              class="w-full h-full object-cover opacity-70 group-hover:opacity-90 group-hover:scale-105 transition-all duration-500"
            />
            <!-- Placeholder if no image -->
            <div v-else class="w-full h-full flex items-center justify-center">
              <div class="text-6xl opacity-20">{ }</div>
            </div>
            <!-- Overlay links -->
            <div class="absolute inset-0 bg-dark/80 flex items-center justify-center gap-4 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
              <a :href="project.gitURL" target="_blank" rel="noopener"
                class="flex items-center gap-2 px-4 py-2 rounded-lg bg-white/10 border border-white/20 text-white text-sm font-display font-medium hover:bg-white/20 transition-colors">
                <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
                Code
              </a>
              <a v-if="project.webURL && project.webURL !== project.gitURL" :href="project.webURL" target="_blank" rel="noopener"
                class="flex items-center gap-2 px-4 py-2 rounded-lg bg-accent/20 border border-accent/40 text-accent text-sm font-display font-medium hover:bg-accent/30 transition-colors">
                <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
                Live
              </a>
            </div>
          </div>

          <!-- Content -->
          <div class="p-6">
            <h3 class="font-display font-bold text-white text-xl mb-2">{{ project.title }}</h3>
            <p class="text-slate-400 text-sm leading-relaxed mb-4">{{ project.description }}</p>
            <div class="flex flex-wrap gap-2">
              <span v-for="tech in project.technologies" :key="tech"
                class="text-xs px-2.5 py-1 rounded-full border border-border text-slate-400 font-medium">
                {{ tech }}
              </span>
            </div>
          </div>
        </article>

        <!-- "More coming soon" card -->
        <div class="glass rounded-2xl overflow-hidden border-dashed flex items-center justify-center min-h-[300px] reveal reveal-delay-3">
          <div class="text-center p-8">
            <div class="w-12 h-12 rounded-full border-2 border-dashed border-border flex items-center justify-center mx-auto mb-4">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#4f8ef7" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
            </div>
            <p class="font-display font-semibold text-slate-500 text-sm">More projects coming soon</p>
            <a href="https://github.com/DanielParin" target="_blank" rel="noopener" class="text-xs text-accent hover:underline mt-2 block">github.com/DanielParin</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import DeshopImage from '@/assets/Deshop.png'

const projects = [
  {
    id: 1,
    title: 'Deshop',
    description: 'Desktop application for managing a store. Features a REST API built from scratch with Spring Boot, connected to a JavaFX frontend for a native desktop experience.',
    image: DeshopImage,
    technologies: ['Java', 'Spring Boot', 'Hibernate', 'MariaDB', 'JavaFX'],
    gitURL: 'https://github.com/DanielParin/Deshop',
    webURL: null,
  },
]
</script>
