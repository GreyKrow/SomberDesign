<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
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
            {{ profileData.ctas.secondary.label }}
          </a>
        </div>
      </div>

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
      </aside>
    </div>
  </section>
</template>

<style scoped lang="scss">
.heroSection {
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
  text-wrap: balance;
}

.heroSection__intro {
  margin-top: 1.25rem;
  max-width: 56ch;
  color: var(--color-ink-dim);
  font-size: clamp(0.97rem, 1.2vw, 1.15rem);
  line-height: 1.72;
}

.heroSection__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 0.65rem;
  margin-top: 1.4rem;
}

.heroSection__button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 46px;
  padding: 0.45rem 1.15rem;
  border: 1px solid var(--color-line-strong);
  color: var(--color-ink);
  font-family: var(--font-mono);
  font-size: 0.71rem;
  letter-spacing: 0.13em;
  text-transform: uppercase;
  transition: transform var(--duration-fast) var(--ease-out), background var(--duration-fast) var(--ease-out);
}

.heroSection__button:hover,
.heroSection__button:focus-visible {
  transform: translate3d(0, -2px, 0);
  background: rgba(243, 245, 248, 0.07);
  outline: none;
}

.heroSection__button--primary {
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
  text-transform: uppercase;
}

.heroSection__signalText {
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
  }
}

@media (max-width: 640px) {
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
  }

  .heroSection__button {
    width: 100%;
  }
}
</style>
