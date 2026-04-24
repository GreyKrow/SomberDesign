<script setup>
const props = defineProps({
  project: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <article class="projectCard line-frame">
    <div class="projectCard__meta">
      <p class="projectCard__status">{{ props.project.status }}</p>
      <p class="projectCard__category">{{ props.project.category }}</p>
    </div>

    <div class="projectCard__core">
      <h3 class="projectCard__title">{{ props.project.title }}</h3>
      <p class="projectCard__summary">{{ props.project.summary }}</p>
    </div>

    <ul class="projectCard__highlights">
      <li v-for="highlight in props.project.highlights" :key="highlight">{{ highlight }}</li>
    </ul>

    <div class="projectCard__stack">
      <span v-for="item in props.project.stack" :key="item">{{ item }}</span>
    </div>

    <div class="projectCard__links">
      <template v-for="link in props.project.links" :key="link.label">
        <a v-if="link.href" :href="link.href" target="_blank" rel="noreferrer" class="projectCard__link">
          {{ link.label }}
        </a>
        <span v-else class="projectCard__link projectCard__link--muted">{{ link.label }}</span>
      </template>
    </div>
  </article>
</template>

<style scoped lang="scss">
.projectCard {
  display: grid;
  grid-template-columns: minmax(140px, 210px) minmax(0, 1.4fr) minmax(0, 1fr) minmax(150px, 220px);
  gap: 0.75rem 1rem;
  align-items: start;
  padding: 1rem;
  transition: border-color var(--duration-fast) var(--ease-out), transform var(--duration-fast) var(--ease-out);
}

.projectCard:hover,
.projectCard:focus-within {
  transform: translate3d(0, -2px, 0);
  border-color: var(--color-line-strong);
}

.projectCard__meta {
  display: grid;
  gap: 0.45rem;
}

.projectCard__status,
.projectCard__category {
  font-family: var(--font-mono);
  font-size: 0.65rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.projectCard__status {
  color: var(--color-ink);
}

.projectCard__category {
  color: var(--color-ink-muted);
}

.projectCard__title {
  font-family: var(--font-display);
  font-size: clamp(1.25rem, 1.8vw, 2rem);
  line-height: 0.94;
  letter-spacing: -0.03em;
}

.projectCard__summary {
  margin-top: 0.5rem;
  color: var(--color-ink-dim);
  font-size: 0.91rem;
  line-height: 1.62;
}

.projectCard__highlights {
  display: grid;
  gap: 0.45rem;
}

.projectCard__highlights li {
  position: relative;
  padding-left: 0.75rem;
  color: var(--color-ink-dim);
  font-size: 0.83rem;
  line-height: 1.52;
}

.projectCard__highlights li::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0.5rem;
  width: 0.33rem;
  height: 1px;
  background: var(--color-line-strong);
}

.projectCard__stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.36rem;
}

.projectCard__stack span {
  display: inline-flex;
  align-items: center;
  min-height: 1.7rem;
  padding: 0.28rem 0.5rem;
  border: 1px solid rgba(243, 245, 248, 0.15);
  color: var(--color-ink-dim);
  font-family: var(--font-mono);
  font-size: 0.62rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.projectCard__links {
  grid-column: 1 / -1;
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
  padding-top: 0.6rem;
  border-top: 1px solid rgba(243, 245, 248, 0.12);
}

.projectCard__link {
  color: var(--color-ink);
  font-family: var(--font-mono);
  font-size: 0.66rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}

.projectCard__link--muted {
  color: var(--color-ink-muted);
}

@media (max-width: 1200px) {
  .projectCard {
    grid-template-columns: minmax(120px, 180px) minmax(0, 1fr);
  }

  .projectCard__stack {
    grid-column: 1 / -1;
  }
}

@media (max-width: 780px) {
  .projectCard {
    grid-template-columns: 1fr;
  }
}
</style>