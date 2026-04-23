<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="heroSection" id="hero" aria-labelledby="hero-title">
    <div>
      <p class="eyebrow">{{ profileData.label }}</p>
      <h1 id="hero-title" class="heroSection__title">{{ profileData.headline }}</h1>
      <p class="heroSection__intro">{{ profileData.intro }}</p>

      <div class="heroSection__actions">
        <a class="heroSection__button" :href="profileData.ctas.primary.href">{{ profileData.ctas.primary.label }}</a>
        <a class="heroSection__button heroSection__button--ghost" :href="profileData.ctas.secondary.href">{{ profileData.ctas.secondary.label }}</a>
      </div>
    </div>

    <aside class="heroSection__signal" aria-label="Current direction">
      <p class="heroSection__signalTitle">{{ profileData.currentSignal.title }}</p>
      <p>{{ profileData.currentSignal.text }}</p>
      <p class="heroSection__meta"><strong>Location:</strong> {{ profileData.location }}</p>
    </aside>
  </section>
</template>

<style scoped lang="scss">
.heroSection {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(260px, 340px);
  gap: 1rem;
  padding: 2rem 1.2rem;
  border: 1px solid var(--color-border);
  border-radius: var(--radius-medium);
  background: var(--color-surface);
}

.heroSection__title {
  margin-top: 1rem;
  max-width: 14ch;
  font-family: var(--font-display);
  font-size: clamp(2rem, 7vw, 3.6rem);
  line-height: 1.02;
  color: var(--color-text-strong);
}

.heroSection__intro {
  margin-top: 0.9rem;
  max-width: 58ch;
}

.heroSection__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-top: 1.2rem;
}

.heroSection__button {
  padding: 0.7rem 0.95rem;
  border: 1px solid var(--color-border);
  border-radius: var(--radius-small);
  font-weight: 700;
  background: var(--color-accent);
  color: #162130;
}

.heroSection__button--ghost {
  background: transparent;
  color: var(--color-text-strong);
}

.heroSection__signal {
  padding: 1rem;
  border: 1px solid var(--color-border);
  border-radius: var(--radius-small);
  background: var(--color-surface-soft);
  color: var(--color-text-base);
}

.heroSection__signalTitle {
  margin-bottom: 0.45rem;
  color: var(--color-accent);
  font-size: 0.82rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.heroSection__meta {
  margin-top: 0.8rem;
  color: var(--color-text-muted);
  font-size: 0.93rem;
}

@media (max-width: 840px) {
  .heroSection {
    grid-template-columns: 1fr;
  }
}
</style>
