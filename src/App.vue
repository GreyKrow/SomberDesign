<script setup>
<<<<<<< HEAD
import { onBeforeUnmount, onMounted, ref } from 'vue'
=======
>>>>>>> f42ff6b (Changes)
import inSiteHeader from './components/inSiteHeader.vue'
import inHeroSection from './components/inHeroSection.vue'
import inAboutSection from './components/inAboutSection.vue'
import inProjectsSection from './components/inProjectsSection.vue'
import inContactSection from './components/inContactSection.vue'
import inSiteFooter from './components/inSiteFooter.vue'
<<<<<<< HEAD

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
=======
import inSnowLayer from './components/inSnowLayer.vue'
</script>

<template>
  <div class="app">
    <div class="app__backdrop" aria-hidden="true"></div>
    <div class="app__noise" aria-hidden="true"></div>
    <div class="app__vignette" aria-hidden="true"></div>
    <inSnowLayer />

    <inSiteHeader />

    <main>
>>>>>>> f42ff6b (Changes)
      <inHeroSection id="hero" class="section-anchor" data-section />
      <inAboutSection id="about" class="section-anchor" data-section />
      <inProjectsSection id="projects" class="section-anchor" data-section />
      <inContactSection id="contact" class="section-anchor" data-section />
    </main>

    <inSiteFooter />
  </div>
</template>

<style scoped lang="scss">
<<<<<<< HEAD
.appShell {
=======
.app {
>>>>>>> f42ff6b (Changes)
  position: relative;
  isolation: isolate;
  min-height: 100vh;
  overflow: clip;
}

<<<<<<< HEAD
.appBackdrop,
.appOverlay {
=======
.app__backdrop,
.app__noise,
.app__vignette {
>>>>>>> f42ff6b (Changes)
  position: fixed;
  inset: 0;
  pointer-events: none;
}

<<<<<<< HEAD
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
=======
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
>>>>>>> f42ff6b (Changes)
}
</style>
