<template>
  <section id="skills" class="py-28 relative">
    <div class="absolute left-0 bottom-0 w-[500px] h-[300px] rounded-full bg-accent/5 blur-[100px] pointer-events-none"></div>

    <div class="max-w-6xl mx-auto px-6">
      <div class="mb-16 reveal">
        <p class="section-tag mb-3">What I work with</p>
        <h2 class="font-display font-bold text-4xl sm:text-5xl text-white">My <span class="gradient-text">Skills</span></h2>
      </div>

      <div class="space-y-12">
        <div v-for="(category, ci) in categories" :key="category.name" :class="['reveal', `reveal-delay-${ci + 1}`]">
          <h3 class="font-display text-sm font-semibold text-slate-500 uppercase tracking-widest mb-5">{{ category.name }}</h3>
          <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-3">
            <div v-for="skill in category.skills" :key="skill.name"
              class="glass rounded-xl p-4 flex flex-col items-center gap-3 hover:border-accent/40 hover:-translate-y-1 transition-all duration-300 cursor-default group">
              <!-- SVG icon or img -->
              <template v-if="skill.svg">
                <div class="w-10 h-10 flex items-center justify-center group-hover:scale-110 transition-transform duration-300" v-html="skill.svg"></div>
              </template>
              <template v-else>
                <img :src="skill.icon" :alt="skill.name" class="w-10 h-10 object-contain group-hover:scale-110 transition-transform duration-300" />
              </template>
              <span class="text-xs font-display font-semibold text-slate-400 group-hover:text-white transition-colors text-center">{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>

const categories = [
  {
    name: 'Languages',
    skills: [
      { name: 'Java', icon: '/DanielPaz/icons/java.svg' },
      { name: 'Go', icon: '/DanielPaz/icons/go.svg' },
      { name: 'Python', icon: '/DanielPaz/icons/python.svg' },
      { name: 'JavaScript', icon: '/DanielPaz/icons/javascript.svg' },
      { name: 'C', icon: '/DanielPaz/icons/c.svg' },
      { name: 'Dart', icon: '/DanielPaz/icons/dart.svg' },
    ]
  },
  {
    name: 'Web Development',
    skills: [
      { name: 'Vue', icon: '/DanielPaz/icons/vue.svg' },
      { name: 'Angular', icon: '/DanielPaz/icons/angular.svg' },
      { name: 'HTML', icon: '/DanielPaz/icons/html.svg' },
      { name: 'CSS', icon: '/DanielPaz/icons/css.svg' },
    ]
  },
  {
    name: 'Mobile Development',
    skills: [
      { name: 'Swift (iOS)', icon: '/DanielPaz/icons/swift.svg' },
      { name: 'Kotlin (Android)', icon: '/DanielPaz/icons/kotlin.svg' },
      {name: 'Flutter', icon: '/DanielPaz/icons/flutter.svg' },
    ]
  },
  {
    name: 'Backend & Frameworks',
    skills: [
      { name: 'Spring', icon: '/DanielPaz/icons/spring.svg' },
      { name: 'Hibernate', icon: '/DanielPaz/icons/hibernate.svg' },
    ]
  },
  {
    name: 'Databases',
    skills: [
      { name: 'SQL', icon: '/DanielPaz/icons/sql.svg' },
      { name: 'MongoDB', icon: '/DanielPaz/icons/mongo.svg' },
    ]
  },
  {
    name: 'Tools & Others',
    skills: [
      { name: 'Git', icon: '/DanielPaz/icons/git.svg' },
      { name: 'Linux', icon: '/DanielPaz/icons/linux.svg' },
    ]
  },
]
</script>
