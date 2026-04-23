<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="aboutSection" id="about" aria-labelledby="about-title">
    <p class="eyebrow">About</p>
    <h2 id="about-title" class="aboutSection__title">Simple process. Useful outcomes.</h2>
    <p class="aboutSection__text">{{ profileData.summary }}</p>

    <ul class="aboutSection__list">
      <li v-for="principle in profileData.principles" :key="principle">{{ principle }}</li>
    </ul>
  </section>
</template>

<style scoped lang="scss">
.aboutSection {
  padding: 2rem 0;
  border-bottom: 3px solid var(--color-border);
}

.aboutSection__title {
  margin-top: 0.9rem;
  font-family: var(--font-display);
  font-size: clamp(1.6rem, 5vw, 2.4rem);
  line-height: 1.1;
}

.aboutSection__text {
  margin-top: 0.9rem;
  max-width: 64ch;
}

.aboutSection__list {
  margin-top: 1rem;
  list-style: square;
  padding-left: 1.25rem;
  display: grid;
  gap: 0.4rem;
}
</style>
