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
        .sort((first, second) => second.intersectionRatio - first.intersectionRatio)

      if (visibleSections.length > 0) {
        activeSection.value = visibleSections[0].target.id
      }
    },
    {
      threshold: [0.25, 0.45, 0.6],
      rootMargin: '-10% 0px -35% 0px',
    },
  )

  sections.forEach(section => observer.observe(section))
})

onBeforeUnmount(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<template>
  <div class="appShell">
    <div class="appBackdrop" aria-hidden="true"></div>
    <div class="appOverlay" aria-hidden="true"></div>

    <inSiteHeader :active-section="activeSection" />

    <main class="appMain">
      <inHeroSection id="hero" class="section-anchor" data-section />
      <inAboutSection id="about" class="section-anchor" data-section />
      <inProjectsSection id="projects" class="section-anchor" data-section />
      <inContactSection id="contact" class="section-anchor" data-section />
    </main>

    <inSiteFooter />
  </div>
</template>

<style scoped lang="scss">
.appShell {
  position: relative;
  isolation: isolate;
  min-height: 100vh;
  overflow: clip;
}

.appBackdrop,
.appOverlay {
  position: fixed;
  inset: 0;
  pointer-events: none;
}

.appBackdrop {
  z-index: -3;
  background-image: url('/assets/images/graykrowForest.png');
  background-position: center bottom;
  background-size: cover;
  background-repeat: no-repeat;
  transform: scale(1.04);
}

.appOverlay {
  z-index: -2;
  background:
    linear-gradient(180deg, rgba(11, 16, 23, 0.48) 0%, rgba(11, 16, 23, 0.72) 34%, rgba(11, 16, 23, 0.88) 100%),
    radial-gradient(circle at top center, rgba(182, 202, 229, 0.12), transparent 48%);
}

.appMain {
  position: relative;
  z-index: 1;
}
</style>
