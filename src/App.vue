<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'
import inSiteHeader from './components/inSiteHeader.vue'
import inHeroSection from './components/inHeroSection.vue'
import inAboutSection from './components/inAboutSection.vue'
import inProjectsSection from './components/inProjectsSection.vue'
import inContactSection from './components/inContactSection.vue'
import inSiteFooter from './components/inSiteFooter.vue'
import inSnowLayer from './components/inSnowLayer.vue'

const activeSection = ref('hero')
let observer

onMounted(() => {
  const sections = document.querySelectorAll('[data-section]')

  observer = new IntersectionObserver(
    entries => {
      const visibleSections = entries
        .filter(entry => entry.isIntersecting)
        .sort((first, second) => second.intersectionRatio - first.intersectionRatio)

      if (visibleSections.length > 0) {
        activeSection.value = visibleSections[0].target.id
      }
    },
    {
      threshold: [0.35, 0.55, 0.75],
      rootMargin: '-12% 0px -42% 0px',
    },
  )

  sections.forEach(section => observer.observe(section))
})

onBeforeUnmount(() => {
  observer?.disconnect()
})
</script>

<template>
  <div class="app">
    <div class="app__backdrop" aria-hidden="true"></div>
    <div class="app__noise" aria-hidden="true"></div>
    <div class="app__vignette" aria-hidden="true"></div>
    <inSnowLayer />

    <inSiteHeader :active-section="activeSection" />

    <main>
      <inHeroSection id="hero" class="section-anchor" data-section />
      <inAboutSection id="about" class="section-anchor" data-section />
      <inProjectsSection id="projects" class="section-anchor" data-section />
      <inContactSection id="contact" class="section-anchor" data-section />
    </main>

    <inSiteFooter />
  </div>
</template>

<style scoped lang="scss">
.app {
  position: relative;
  isolation: isolate;
  min-height: 100vh;
  overflow: clip;
}

.app__backdrop,
.app__noise,
.app__vignette {
  position: fixed;
  inset: 0;
  pointer-events: none;
}

.app__backdrop {
  z-index: -4;
  background:
    linear-gradient(180deg, rgba(7, 9, 13, 0.88) 8%, rgba(7, 9, 13, 0.72) 50%, rgba(7, 9, 13, 0.94) 100%),
    url('/assets/images/graykrowForest.png') center 85% / cover no-repeat;
  transform: scale(1.06);
}

.app__noise {
  z-index: -3;
  opacity: 0.15;
  background-image:
    radial-gradient(circle at 10% 20%, rgba(255, 255, 255, 0.2) 0 0.7px, transparent 0.8px),
    radial-gradient(circle at 70% 40%, rgba(255, 255, 255, 0.13) 0 0.8px, transparent 0.9px);
  background-size: 5px 5px, 7px 7px;
}

.app__vignette {
  z-index: -2;
  background: radial-gradient(circle at 50% 35%, transparent 0%, rgba(7, 9, 13, 0.65) 75%);
}
</style>
