<template>
  <section id="contact" class="py-28 relative">
    <!-- Background glows -->
    <div class="absolute inset-0 pointer-events-none overflow-hidden">
      <div class="absolute bottom-0 left-1/2 -translate-x-1/2 w-[600px] h-[300px] rounded-full bg-accent/8 blur-[120px]"></div>
    </div>

    <div class="max-w-6xl mx-auto px-6">
      <!-- Section header -->
      <div class="mb-16 reveal">
        <p class="section-tag mb-3">Let's talk</p>
        <h2 class="font-display font-bold text-4xl sm:text-5xl text-white">Get in <span class="gradient-text">touch</span></h2>
      </div>

      <div class="grid lg:grid-cols-2 gap-12 items-start">
        <div class="space-y-8">
          <p class="text-slate-300 text-lg leading-relaxed reveal reveal-delay-1">
            I'm currently open to collaborating on interesting projects,
             connecting with like-minded people, and having conversations
              around technology. While I'm not actively looking for a 
              full-time role, I'm always happy to hear about compelling 
              opportunities.
          </p>

          <div class="space-y-4 reveal reveal-delay-2">
            <a
              v-for="link in contactLinks"
              :key="link.label"
              :href="link.href"
              :target="link.external ? '_blank' : undefined"
              rel="noopener"
              class="flex items-center gap-4 p-4 glass rounded-xl hover:border-accent/40 hover:-translate-x-0 group transition-all duration-300"
            >
              <div class="w-10 h-10 rounded-lg bg-accent/10 flex items-center justify-center text-accent flex-shrink-0 group-hover:bg-accent/20 transition-colors">
                <component :is="'svg'" v-bind="link.iconAttrs" v-html="link.iconPath"></component>
              </div>
              <div>
                <p class="text-xs font-display font-semibold text-slate-500 uppercase tracking-wider mb-0.5">{{ link.label }}</p>
                <p class="text-white font-medium group-hover:text-accent transition-colors">{{ link.value }}</p>
              </div>
              <svg class="ml-auto text-slate-600 group-hover:text-accent transition-colors" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
            </a>
          </div>
        </div>

        <!-- Right: simple message card -->
        <div class="glass rounded-2xl p-8 reveal reveal-delay-3">
          <h3 class="font-display font-bold text-white text-xl mb-2">Send me a message</h3>
          <p class="text-slate-500 text-sm mb-6">I'll get back to you as soon as possible.</p>

          <div class="space-y-4">
            <div>
              <label class="block text-xs font-display font-semibold text-slate-400 uppercase tracking-wider mb-2">Name</label>
              <input
                v-model="form.name"
                type="text"
                placeholder="Your name"
                class="w-full bg-dark border border-border rounded-lg px-4 py-3 text-white placeholder-slate-600 text-sm focus:outline-none focus:border-accent transition-colors"
              />
            </div>
            <div>
              <label class="block text-xs font-display font-semibold text-slate-400 uppercase tracking-wider mb-2">Email</label>
              <input
                v-model="form.email"
                type="email"
                placeholder="your@email.com"
                class="w-full bg-dark border border-border rounded-lg px-4 py-3 text-white placeholder-slate-600 text-sm focus:outline-none focus:border-accent transition-colors"
              />
            </div>
            <div>
              <label class="block text-xs font-display font-semibold text-slate-400 uppercase tracking-wider mb-2">Message</label>
              <textarea
                v-model="form.message"
                rows="4"
                placeholder="What's on your mind?"
                class="w-full bg-dark border border-border rounded-lg px-4 py-3 text-white placeholder-slate-600 text-sm focus:outline-none focus:border-accent transition-colors resize-none"
              ></textarea>
            </div>

            <a
              :href="mailtoLink"
              class="btn-primary w-full justify-center"
            >
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
              Send message
            </a>
            <p class="text-center text-slate-600 text-xs">Opens your email client with the message pre-filled.</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const form = ref({ name: '', email: '', message: '' })

const mailtoLink = computed(() => {
  const subject = encodeURIComponent(`Contact from ${form.value.name || 'your portfolio'}`)
  const body = encodeURIComponent(form.value.message || '')
  return `mailto:dpazrincon@gmail.com?subject=${subject}&body=${body}`
})

const contactLinks = [
  {
    label: 'Email',
    value: 'dpazrincon@gmail.com',
    href: 'mailto:dpazrincon@gmail.com',
    external: false,
    iconAttrs: { xmlns: 'http://www.w3.org/2000/svg', width: '18', height: '18', viewBox: '0 0 24 24', fill: 'none', stroke: 'currentColor', 'stroke-width': '1.8', 'stroke-linecap': 'round', 'stroke-linejoin': 'round' },
    iconPath: '<rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/>',
  },
  {
    label: 'GitHub',
    value: 'github.com/DanielParin',
    href: 'https://github.com/DanielParin',
    external: true,
    iconAttrs: { xmlns: 'http://www.w3.org/2000/svg', width: '18', height: '18', viewBox: '0 0 24 24', fill: 'currentColor' },
    iconPath: '<path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/>',
  },
  {
    label: 'LinkedIn',
    value: 'Daniel Paz Rincón',
    href: 'https://www.linkedin.com/in/daniel-paz-rincon',
    external: true,
    iconAttrs: { xmlns: 'http://www.w3.org/2000/svg', width: '18', height: '18', viewBox: '0 0 24 24', fill: 'currentColor' },
    iconPath: '<path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>',
  },
]
</script>
