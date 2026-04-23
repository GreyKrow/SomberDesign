<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="heroSection" id="hero" aria-labelledby="hero-title">
    <p class="eyebrow">{{ profileData.label }}</p>
    <h1 id="hero-title" class="heroSection__title">{{ profileData.headline }}</h1>
    <p class="heroSection__intro">{{ profileData.intro }}</p>

    <div class="heroSection__actions">
      <a class="heroSection__button" :href="profileData.ctas.primary.href">{{ profileData.ctas.primary.label }}</a>
      <a class="heroSection__button heroSection__button--ghost" :href="profileData.ctas.secondary.href">{{ profileData.ctas.secondary.label }}</a>
    </div>

    <p class="heroSection__meta"><strong>Location:</strong> {{ profileData.location }}</p>
  </section>
</template>

<style scoped lang="scss">
.heroSection {
  padding: 3rem 0 2rem;
  border-bottom: 3px solid var(--color-border);
}

.heroSection__title {
  margin-top: 1rem;
  max-width: 14ch;
  font-family: var(--font-display);
  font-size: clamp(2rem, 7vw, 4rem);
  line-height: 1;
  letter-spacing: -0.02em;
  color: var(--color-text-strong);
}

.heroSection__intro {
  margin-top: 1rem;
  max-width: 60ch;
  font-size: 1.05rem;
}

.heroSection__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-top: 1.4rem;
}

.heroSection__button {
  padding: 0.75rem 1rem;
  border: 2px solid var(--color-border);
  font-weight: 800;
  background: var(--color-accent);
}

.heroSection__button--ghost {
  background: var(--color-surface);
}

.heroSection__meta {
  margin-top: 1rem;
  font-size: 0.95rem;
  color: var(--color-text-muted);
}
</style>
