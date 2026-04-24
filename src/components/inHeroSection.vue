<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="heroSection" id="hero">
    <div class="heroSection__inner">
      <div class="heroSection__content">
        <p class="eyebrow">{{ profileData.label }}</p>

        <h1 class="heroSection__title">
          {{ profileData.headline }}
        </h1>

        <p class="heroSection__intro">
          {{ profileData.intro }}
        </p>

        <div class="heroSection__actions">
          <a
            class="heroSection__button heroSection__button--primary"
            :href="profileData.ctas.primary.href"
          >
            {{ profileData.ctas.primary.label }}
          </a>

          <a
            class="heroSection__button heroSection__button--secondary"
            :href="profileData.ctas.secondary.href"
          >
            {{ profileData.ctas.secondary.label }}
          </a>
        </div>
      </div>

      <aside class="heroSection__signal" aria-label="Current direction">
        <p class="heroSection__signalEyebrow">
          {{ profileData.currentSignal.title }}
        </p>

        <p class="heroSection__signalText">
          {{ profileData.currentSignal.text }}
        </p>

        <div class="heroSection__signalMeta">
          <div class="heroSection__metaItem">
            <span class="heroSection__metaLabel">Working from</span>
            <strong class="heroSection__metaValue">{{ profileData.location }}</strong>
          </div>

          <div class="heroSection__metaItem">
            <span class="heroSection__metaLabel">Availability</span>
            <strong class="heroSection__metaValue">{{ profileData.availability }}</strong>
          </div>
        </div>
      </aside>
    </div>
  </section>
</template>

<style scoped lang="scss">
.heroSection {
  display: grid;
  align-items: center;
  min-height: 68svh;
  padding: 5.4rem 0 2.2rem;
}

.heroSection__inner {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(280px, 360px);
  gap: 1.6rem;
  align-items: center;
  width: var(--site-width);
  margin: 0 auto;
}

.heroSection__content {
  max-width: 32rem;
}

.heroSection__title {
  max-width: 14ch;
  margin-top: 0.9rem;
  color: var(--color-text-strong);
  font-family: var(--font-display);
  font-size: clamp(2rem, 3.4vw, 3.1rem);
  line-height: 1.08;
  letter-spacing: -0.025em;
  text-wrap: balance;
}

.heroSection__intro {
  max-width: 33rem;
  margin-top: 1rem;
  color: var(--color-text-base);
  font-size: 1rem;
  line-height: 1.8;
}

.heroSection__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-top: 1.6rem;
}

.heroSection__button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 10.5rem;
  min-height: 3rem;
  padding: 0.78rem 1rem;
  border: 1px solid transparent;
  border-radius: 14px;
  font-size: 0.92rem;
  font-weight: 700;
  transition:
    transform var(--transition-standard),
    border-color var(--transition-standard),
    background-color var(--transition-standard),
    color var(--transition-standard),
    box-shadow var(--transition-standard);
}

.heroSection__button:hover,
.heroSection__button:focus-visible {
  transform: translateY(-2px);
  outline: none;
}

.heroSection__button--primary {
  background: rgba(231, 237, 244, 0.9);
  color: var(--color-ink-900);
  box-shadow: 0 10px 20px rgba(5, 9, 14, 0.14);
}

.heroSection__button--secondary {
  border-color: rgba(214, 224, 236, 0.1);
  background: rgba(223, 232, 242, 0.025);
  color: var(--color-text-strong);
}

.heroSection__signal {
  align-self: center;
  padding: 1.15rem 1.1rem;
  border: 1px solid rgba(214, 224, 236, 0.06);
  border-radius: 20px;
  background:
    linear-gradient(180deg, rgba(23, 30, 39, 0.68), rgba(16, 21, 29, 0.72)),
    rgba(10, 15, 22, 0.16);
  box-shadow:
    0 12px 24px rgba(4, 8, 14, 0.12),
    inset 0 1px 0 rgba(255, 255, 255, 0.015);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
}

.heroSection__signalEyebrow {
  color: rgba(192, 211, 232, 0.78);
  font-family: var(--font-accent);
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}

.heroSection__signalText {
  margin-top: 0.85rem;
  color: var(--color-text-base);
  font-size: 0.94rem;
  line-height: 1.75;
}

.heroSection__signalMeta {
  display: grid;
  gap: 0.9rem;
  margin-top: 1.05rem;
  padding-top: 1rem;
  border-top: 1px solid rgba(214, 224, 236, 0.06);
}

.heroSection__metaItem {
  display: grid;
  gap: 0.28rem;
}

.heroSection__metaLabel {
  color: var(--color-text-muted);
  font-family: var(--font-accent);
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.heroSection__metaValue {
  color: var(--color-text-strong);
  font-size: 0.9rem;
  line-height: 1.65;
  font-weight: 600;
}

@media (max-width: 980px) {
  .heroSection {
    min-height: auto;
    padding-top: 5.8rem;
    padding-bottom: 2.4rem;
  }

  .heroSection__inner {
    grid-template-columns: 1fr;
    gap: 1.15rem;
    align-items: start;
  }

  .heroSection__content {
    max-width: 100%;
  }

  .heroSection__signal {
    max-width: 32rem;
  }
}

@media (max-width: 640px) {
  .heroSection__title {
    font-size: clamp(1.8rem, 8vw, 2.5rem);
    line-height: 1.1;
  }

  .heroSection__intro {
    font-size: 0.96rem;
    line-height: 1.75;
  }

  .heroSection__button {
    width: 100%;
  }

  .heroSection__signal {
    border-radius: 18px;
  }
  .heroSection {
  padding-top: 5.2rem;
  padding-bottom: 2rem;
}
}
</style>