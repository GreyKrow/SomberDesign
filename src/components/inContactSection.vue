<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="contactSection" id="contact" aria-labelledby="contact-title">
    <p class="eyebrow">Contact</p>
    <h2 id="contact-title" class="contactSection__title">Let's build something useful.</h2>
    <p class="contactSection__text">{{ profileData.availability }}</p>

    <ul class="contactSection__list">
      <li v-for="link in profileData.contactLinks" :key="link.label">
        <span>{{ link.label }}:</span>
        <a v-if="link.href" :href="link.href" target="_blank" rel="noreferrer">{{ link.value }}</a>
        <span v-else>{{ link.value }}</span>
      </li>
    </ul>
  </section>
</template>

<style scoped lang="scss">
.contactSection {
  padding: 2rem 0;
  border-bottom: 3px solid var(--color-border);
}

.contactSection__title {
  margin-top: 0.9rem;
  font-family: var(--font-display);
  font-size: clamp(1.6rem, 5vw, 2.3rem);
}

.contactSection__text {
  margin-top: 0.8rem;
}

.contactSection__list {
  margin-top: 1rem;
  list-style: none;
  display: grid;
  gap: 0.55rem;
}

.contactSection__list li {
  display: flex;
  gap: 0.5rem;
  align-items: baseline;
}

.contactSection__list span:first-child {
  font-weight: 800;
}

.contactSection__list a {
  border-bottom: 2px solid var(--color-border);
}
</style>
