<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="contactSection" id="contact">
    <div class="contactSection__inner">
      <div class="contactSection__copy">
        <p class="eyebrow">Contact</p>

        <h2 class="contactSection__title">
          Reach out when the work makes sense.
        </h2>

        <p class="contactSection__text">
          {{ profileData.availability }}
        </p>

        <p class="contactSection__subtext">
          SomberDesign is built around smaller, more intentional work. If you
          have something personal, focused, or identity-led in mind, that is
          usually the best fit.
        </p>

        <p class="contactSection__location">
          {{ profileData.location }}
        </p>
      </div>

      <div class="contactSection__panel">
        <div class="contactSection__panelHead">
          <p class="contactSection__panelLabel">Contact points</p>
          <p class="contactSection__panelNote">Keep it direct.</p>
        </div>

        <ul class="contactSection__links">
          <li
            v-for="link in profileData.contactLinks"
            :key="link.label"
            class="contactSection__item"
          >
            <span class="contactSection__label">{{ link.label }}</span>

            <a
              v-if="link.href"
              :href="link.href"
              class="contactSection__value"
              target="_blank"
              rel="noreferrer"
            >
              {{ link.value }}
            </a>

            <span
              v-else
              class="contactSection__value contactSection__value--placeholder"
            >
              {{ link.value }}
            </span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.contactSection {
  padding: 2.4rem 0 5rem;
}

.contactSection__inner {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(300px, 0.9fr);
  gap: 2rem;
  align-items: start;
  width: var(--site-width);
  margin: 0 auto;
  padding-top: 1.4rem;
  border-top: 1px solid rgba(214, 224, 236, 0.08);
}

.contactSection__copy {
  max-width: 36rem;
}

.contactSection__title {
  max-width: 16ch;
  margin-top: 0.9rem;
  color: var(--color-text-strong);
  font-family: var(--font-display);
  font-size: clamp(1.6rem, 3vw, 2.3rem);
  line-height: 1.08;
  letter-spacing: -0.025em;
  text-wrap: balance;
}

.contactSection__text {
  max-width: 32rem;
  margin-top: 1rem;
  color: var(--color-text-base);
  font-size: 0.98rem;
  line-height: 1.8;
}

.contactSection__subtext {
  max-width: 31rem;
  margin-top: 0.85rem;
  color: var(--color-text-muted);
  font-size: 0.94rem;
  line-height: 1.8;
}

.contactSection__location {
  margin-top: 1rem;
  color: rgba(192, 211, 232, 0.76);
  font-family: var(--font-accent);
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.contactSection__panel {
  display: grid;
  gap: 1rem;
  min-width: 0;
}

.contactSection__panelHead {
  display: flex;
  justify-content: space-between;
  gap: 1rem;
  align-items: baseline;
  padding-bottom: 0.75rem;
  border-bottom: 1px solid rgba(214, 224, 236, 0.08);
}

.contactSection__panelLabel {
  color: rgba(192, 211, 232, 0.78);
  font-family: var(--font-accent);
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}

.contactSection__panelNote {
  color: var(--color-text-muted);
  font-size: 0.84rem;
  line-height: 1.5;
}

.contactSection__links {
  display: grid;
  gap: 0;
}

.contactSection__item {
  display: grid;
  grid-template-columns: minmax(90px, 110px) minmax(0, 1fr);
  gap: 1rem;
  align-items: start;
  padding: 0.95rem 0;
  border-bottom: 1px solid rgba(214, 224, 236, 0.08);
}

.contactSection__item:last-child {
  padding-bottom: 0;
  border-bottom: 0;
}

.contactSection__label {
  color: var(--color-text-muted);
  font-family: var(--font-accent);
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.contactSection__value {
  position: relative;
  width: fit-content;
  color: var(--color-text-strong);
  font-size: 0.96rem;
  font-weight: 600;
  line-height: 1.7;
  transition: color var(--transition-standard);
}

.contactSection__value::after {
  content: '';
  position: absolute;
  right: 0;
  bottom: -0.14rem;
  left: 0;
  height: 1px;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(192, 211, 232, 0.8),
    transparent
  );
  opacity: 0;
  transform: scaleX(0.72);
  transform-origin: center;
  transition:
    opacity var(--transition-standard),
    transform var(--transition-standard);
}

.contactSection__value:hover,
.contactSection__value:focus-visible {
  color: var(--color-text-strong);
  outline: none;
}

.contactSection__value:hover::after,
.contactSection__value:focus-visible::after {
  opacity: 1;
  transform: scaleX(1);
}

.contactSection__value--placeholder {
  color: rgba(232, 239, 247, 0.72);
}

.contactSection__value--placeholder::after {
  display: none;
}

@media (max-width: 900px) {
  .contactSection {
    padding-top: 2rem;
    padding-bottom: 4.2rem;
  }

  .contactSection__inner {
    grid-template-columns: 1fr;
    gap: 1.45rem;
  }

  .contactSection__copy {
    max-width: 100%;
  }

  .contactSection__panel {
    max-width: 38rem;
  }
}

@media (max-width: 640px) {
  .contactSection {
    padding-top: 1.8rem;
    padding-bottom: 3.6rem;
  }

  .contactSection__inner {
    gap: 1.2rem;
    padding-top: 1.1rem;
  }

  .contactSection__title {
    font-size: clamp(1.4rem, 7vw, 1.95rem);
    line-height: 1.12;
  }

  .contactSection__text,
  .contactSection__subtext,
  .contactSection__value {
    font-size: 0.93rem;
    line-height: 1.72;
  }

  .contactSection__item {
    grid-template-columns: 1fr;
    gap: 0.35rem;
    padding: 0.85rem 0;
  }

  .contactSection__panelHead {
    flex-direction: column;
    align-items: start;
    gap: 0.3rem;
  }
}
</style>