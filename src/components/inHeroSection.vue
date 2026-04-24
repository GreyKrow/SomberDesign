<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
<<<<<<< HEAD
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
=======
  <section class="heroSection">
    <div class="shell-grid heroSection__inner">
      <div class="heroSection__copy">
        <p class="kicker">{{ profileData.label }}</p>
        <h1 class="heroSection__title">{{ profileData.headline }}</h1>
        <p class="heroSection__intro">{{ profileData.intro }}</p>

        <div class="heroSection__actions">
          <a class="heroSection__button heroSection__button--primary" :href="profileData.ctas.primary.href">
            {{ profileData.ctas.primary.label }}
          </a>
          <a class="heroSection__button" :href="profileData.ctas.secondary.href">
>>>>>>> f42ff6b (Changes)
            {{ profileData.ctas.secondary.label }}
          </a>
        </div>
      </div>

<<<<<<< HEAD
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
=======
      <aside class="heroSection__signal line-frame" aria-label="Current signal and availability">
        <p class="heroSection__signalLabel">{{ profileData.currentSignal.title }}</p>
        <p class="heroSection__signalText">{{ profileData.currentSignal.text }}</p>

        <dl class="heroSection__meta">
          <div>
            <dt>Location</dt>
            <dd>{{ profileData.location }}</dd>
          </div>
          <div>
            <dt>Status</dt>
            <dd>{{ profileData.availability }}</dd>
          </div>
        </dl>
>>>>>>> f42ff6b (Changes)
      </aside>
    </div>
  </section>
</template>

<style scoped lang="scss">
.heroSection {
<<<<<<< HEAD
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
=======
  padding: clamp(3rem, 7vw, 5.4rem) 0 var(--section-pad-y-tight);
}

.heroSection__inner {
  align-items: end;
}

.heroSection__copy {
  grid-column: 1 / span 8;
}

.heroSection__title {
  margin-top: 0.95rem;
  max-width: 15ch;
  font-family: var(--font-display);
  font-size: clamp(2.35rem, 5.7vw, 5.05rem);
  font-weight: 500;
  letter-spacing: -0.035em;
  line-height: 0.96;
>>>>>>> f42ff6b (Changes)
  text-wrap: balance;
}

.heroSection__intro {
<<<<<<< HEAD
  max-width: 33rem;
  margin-top: 1rem;
  color: var(--color-text-base);
  font-size: 1rem;
  line-height: 1.8;
=======
  margin-top: 1.25rem;
  max-width: 56ch;
  color: var(--color-ink-dim);
  font-size: clamp(0.97rem, 1.2vw, 1.15rem);
  line-height: 1.72;
>>>>>>> f42ff6b (Changes)
}

.heroSection__actions {
  display: flex;
  flex-wrap: wrap;
<<<<<<< HEAD
  gap: 0.75rem;
  margin-top: 1.6rem;
=======
  gap: 0.65rem;
  margin-top: 1.4rem;
>>>>>>> f42ff6b (Changes)
}

.heroSection__button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
<<<<<<< HEAD
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
=======
  min-height: 46px;
  padding: 0.45rem 1.15rem;
  border: 1px solid var(--color-line-strong);
  color: var(--color-ink);
  font-family: var(--font-mono);
  font-size: 0.71rem;
  letter-spacing: 0.13em;
  text-transform: uppercase;
  transition: transform var(--duration-fast) var(--ease-out), background var(--duration-fast) var(--ease-out);
>>>>>>> f42ff6b (Changes)
}

.heroSection__button:hover,
.heroSection__button:focus-visible {
<<<<<<< HEAD
  transform: translateY(-2px);
=======
  transform: translate3d(0, -2px, 0);
  background: rgba(243, 245, 248, 0.07);
>>>>>>> f42ff6b (Changes)
  outline: none;
}

.heroSection__button--primary {
<<<<<<< HEAD
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
=======
  background: var(--color-accent);
  color: var(--color-bg);
  border-color: var(--color-accent);
}

.heroSection__signal {
  grid-column: 9 / -1;
  display: grid;
  gap: 1rem;
  padding: 1rem;
}

.heroSection__signalLabel {
  color: var(--color-ink-muted);
  font-family: var(--font-mono);
  font-size: 0.64rem;
  letter-spacing: 0.16em;
>>>>>>> f42ff6b (Changes)
  text-transform: uppercase;
}

.heroSection__signalText {
<<<<<<< HEAD
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
=======
  color: var(--color-ink-dim);
  font-size: 0.9rem;
  line-height: 1.75;
}

.heroSection__meta {
  display: grid;
  gap: 0.75rem;
  margin-top: 0.2rem;
  padding-top: 0.85rem;
  border-top: 1px solid rgba(243, 245, 248, 0.12);
}

.heroSection__meta dt {
  margin-bottom: 0.26rem;
  color: var(--color-ink-muted);
  font-family: var(--font-mono);
  font-size: 0.64rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}

.heroSection__meta dd {
  margin: 0;
  color: var(--color-ink);
  font-size: 0.86rem;
  line-height: 1.5;
}

@media (max-width: 1000px) {
  .heroSection__copy,
  .heroSection__signal {
    grid-column: 1 / -1;
  }

  .heroSection__signal {
    max-width: 34rem;
  }
}

@media (max-width: 900px) {
  .heroSection {
    padding-top: 2.35rem;
  }

  .heroSection__title {
    max-width: 15ch;
    font-size: clamp(2.05rem, 8.5vw, 3.6rem);
    letter-spacing: -0.03em;
    line-height: 0.98;
  }

  .heroSection__intro {
    max-width: 46ch;
>>>>>>> f42ff6b (Changes)
  }
}

@media (max-width: 640px) {
<<<<<<< HEAD
  .heroSection__title {
    font-size: clamp(1.8rem, 8vw, 2.5rem);
    line-height: 1.1;
  }

  .heroSection__intro {
    font-size: 0.96rem;
    line-height: 1.75;
=======
  .heroSection {
    padding-top: 1.85rem;
  }

  .heroSection__title {
    max-width: 14ch;
    font-size: clamp(1.8rem, 9.4vw, 2.75rem);
    line-height: 1;
  }

  .heroSection__intro {
    margin-top: 1.1rem;
    line-height: 1.66;
  }

  .heroSection__actions {
    gap: 0.5rem;
>>>>>>> f42ff6b (Changes)
  }

  .heroSection__button {
    width: 100%;
  }
<<<<<<< HEAD

  .heroSection__signal {
    border-radius: 18px;
  }
  .heroSection {
  padding-top: 5.2rem;
  padding-bottom: 2rem;
}
=======
>>>>>>> f42ff6b (Changes)
}
</style>