<script setup>
import { profileData } from '../data/inProfileData'
</script>

<template>
  <section class="contactSection">
    <div class="shell-grid contactSection__inner">
      <header class="contactSection__intro">
        <p class="kicker">Contact</p>
        <h2 class="section-title">If it is focused, difficult, and worth crafting — I am interested.</h2>
      </header>

      <div class="contactSection__panel line-frame">
        <p class="contactSection__availability">{{ profileData.availability }}</p>
        <ul>
          <li v-for="link in profileData.contactLinks" :key="link.label">
            <span>{{ link.label }}</span>
            <a v-if="link.href" :href="link.href" target="_blank" rel="noreferrer">{{ link.value }}</a>
            <span v-else>{{ link.value }}</span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.contactSection {
  padding: var(--space-8) 0 var(--space-7);
}

.contactSection__intro {
  grid-column: 1 / span 7;
  display: grid;
  gap: 1rem;
}

.contactSection__panel {
  grid-column: 8 / -1;
  padding: 1rem;
}

.contactSection__availability {
  color: var(--color-ink-dim);
  font-size: 0.98rem;
  line-height: 1.6;
}

.contactSection__panel ul {
  margin-top: 0.9rem;
}

.contactSection__panel li {
  display: flex;
  justify-content: space-between;
  gap: 1rem;
  padding: 0.75rem 0;
  border-top: 1px solid rgba(243, 245, 248, 0.12);
}

.contactSection__panel li span:first-child {
  color: var(--color-ink-muted);
  font-family: var(--font-mono);
  font-size: 0.66rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}

.contactSection__panel a,
.contactSection__panel li span:last-child {
  color: var(--color-ink);
  font-size: 0.93rem;
}

@media (max-width: 900px) {
  .contactSection {
    padding: 3.4rem 0;
  }

  .contactSection__intro,
  .contactSection__panel {
    grid-column: 1 / -1;
  }
}
</style>
