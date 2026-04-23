<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="contactSection" id="contact" aria-labelledby="contact-title">
    <p class="eyebrow">Contact</p>
    <h2 id="contact-title" class="contactSection__title">Open for focused collaborations.</h2>
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
  margin-top: 1rem;
  padding: 1.8rem 1.2rem;
  border: 1px solid var(--color-border);
  border-radius: var(--radius-medium);
  background: var(--color-surface);
}

.contactSection__title {
  margin-top: 0.8rem;
  font-family: var(--font-display);
  font-size: clamp(1.55rem, 5vw, 2.1rem);
  color: var(--color-text-strong);
}

.contactSection__text {
  margin-top: 0.7rem;
  max-width: 58ch;
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
  flex-wrap: wrap;
}

.contactSection__list span:first-child {
  font-weight: 700;
}

.contactSection__list a {
  border-bottom: 1px solid var(--color-border);
  color: var(--color-text-strong);
}
</style>
