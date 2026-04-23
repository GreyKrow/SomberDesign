<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="aboutSection" id="about" aria-labelledby="about-title">
    <p class="eyebrow">About</p>
    <h2 id="about-title" class="aboutSection__title">Focused work, clear outcomes.</h2>
    <p class="aboutSection__text">{{ profileData.summary }}</p>

    <ul class="aboutSection__list">
      <li v-for="principle in profileData.principles" :key="principle">{{ principle }}</li>
    </ul>
  </section>
</template>

<style scoped lang="scss">
.aboutSection {
  margin-top: 1rem;
  padding: 1.8rem 1.2rem;
  border: 1px solid var(--color-border);
  border-radius: var(--radius-medium);
  background: var(--color-surface);
}

.aboutSection__title {
  margin-top: 0.8rem;
  font-family: var(--font-display);
  font-size: clamp(1.55rem, 5vw, 2.2rem);
  color: var(--color-text-strong);
}

.aboutSection__text {
  margin-top: 0.8rem;
  max-width: 62ch;
}

.aboutSection__list {
  margin-top: 1rem;
  list-style: square;
  padding-left: 1.2rem;
  display: grid;
  gap: 0.35rem;
}
</style>
