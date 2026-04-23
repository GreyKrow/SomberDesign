<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'
import inSiteHeader from './components/inSiteHeader.vue'
import inHeroSection from './components/inHeroSection.vue'
import inAboutSection from './components/inAboutSection.vue'
import inProjectsSection from './components/inProjectsSection.vue'
import inContactSection from './components/inContactSection.vue'
import inSiteFooter from './components/inSiteFooter.vue'

const activeSection = ref('hero')
let observer

onMounted(() => {
  const sections = document.querySelectorAll('[data-section]')

  observer = new IntersectionObserver(
    entries => {
      const visibleSections = entries
        .filter(entry => entry.isIntersecting)
        .sort((a, b) => b.intersectionRatio - a.intersectionRatio)

      if (visibleSections.length > 0) {
        activeSection.value = visibleSections[0].target.id
      }
    },
    {
      threshold: [0.3, 0.55],
      rootMargin: '-15% 0px -45% 0px',
    },
  )

  sections.forEach(section => observer.observe(section))
})

onBeforeUnmount(() => {
  observer?.disconnect()
})
</script>

<template>
  <a class="skipLink" href="#main-content">Skip to main content</a>

  <div class="appShell">
    <inSiteHeader :active-section="activeSection" />

    <main id="main-content" class="appMain">
      <inHeroSection id="hero" class="section-anchor" data-section />
      <inAboutSection id="about" class="section-anchor" data-section />
      <inProjectsSection id="projects" class="section-anchor" data-section />
      <inContactSection id="contact" class="section-anchor" data-section />
    </main>

    <inSiteFooter />
  </div>
</template>

<style scoped lang="scss">
.skipLink {
  position: fixed;
  top: 0.5rem;
  left: 0.5rem;
  z-index: 100;
  padding: 0.75rem 1rem;
  border: 2px solid var(--color-text-strong);
  background: var(--color-background);
  color: var(--color-text-strong);
  transform: translateY(-180%);
}

.skipLink:focus {
  transform: translateY(0);
}

.appShell {
  min-height: 100vh;
  background: repeating-linear-gradient(
    0deg,
    var(--color-background),
    var(--color-background) 36px,
    var(--color-background-alt) 36px,
    var(--color-background-alt) 72px
  );
}

.appMain {
  width: var(--site-width);
  margin: 0 auto;
  padding-bottom: 2rem;
}
</style>
