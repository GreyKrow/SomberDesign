<script setup>
const props = defineProps({
  project: {
    type: Object,
    required: true,
  },
})
</script>

<template>
<<<<<<< HEAD
  <article class="projectCard">
    <div class="projectCard__top">
=======
  <article class="projectCard line-frame">
    <div class="projectCard__meta">
>>>>>>> f42ff6b (Changes)
      <p class="projectCard__status">{{ props.project.status }}</p>
      <p class="projectCard__category">{{ props.project.category }}</p>
    </div>

<<<<<<< HEAD
    <div class="projectCard__main">
=======
    <div class="projectCard__core">
>>>>>>> f42ff6b (Changes)
      <h3 class="projectCard__title">{{ props.project.title }}</h3>
      <p class="projectCard__summary">{{ props.project.summary }}</p>
    </div>

<<<<<<< HEAD
    <div class="projectCard__section">
      <p class="projectCard__label">Highlights</p>
      <ul class="projectCard__highlights">
        <li
          v-for="highlight in props.project.highlights"
          :key="highlight"
        >
          {{ highlight }}
        </li>
      </ul>
    </div>

    <div class="projectCard__section">
      <p class="projectCard__label">Stack</p>
      <ul class="projectCard__stack">
        <li
          v-for="item in props.project.stack"
          :key="item"
        >
          {{ item }}
        </li>
      </ul>
=======
    <ul class="projectCard__highlights">
      <li v-for="highlight in props.project.highlights" :key="highlight">{{ highlight }}</li>
    </ul>

    <div class="projectCard__stack">
      <span v-for="item in props.project.stack" :key="item">{{ item }}</span>
>>>>>>> f42ff6b (Changes)
    </div>

    <div class="projectCard__links">
      <template v-for="link in props.project.links" :key="link.label">
<<<<<<< HEAD
        <a
          v-if="link.href"
          :href="link.href"
          class="projectCard__link"
          target="_blank"
          rel="noreferrer"
        >
          {{ link.label }}
        </a>

        <span
          v-else
          class="projectCard__link projectCard__link--muted"
        >
          {{ link.label }}
        </span>
=======
        <a v-if="link.href" :href="link.href" target="_blank" rel="noreferrer" class="projectCard__link">
          {{ link.label }}
        </a>
        <span v-else class="projectCard__link projectCard__link--muted">{{ link.label }}</span>
>>>>>>> f42ff6b (Changes)
      </template>
    </div>
  </article>
</template>

<style scoped lang="scss">
.projectCard {
  display: grid;
<<<<<<< HEAD
  grid-template-rows: auto auto auto auto 1fr;
  gap: 1rem;
  min-height: 100%;
  padding: 1.2rem 1.1rem 1.15rem;
  border: 1px solid rgba(214, 224, 236, 0.06);
  border-radius: 20px;
  background:
    linear-gradient(180deg, rgba(21, 28, 36, 0.58), rgba(15, 20, 27, 0.64)),
    rgba(10, 15, 22, 0.14);
  box-shadow:
    0 10px 22px rgba(4, 8, 14, 0.08),
    inset 0 1px 0 rgba(255, 255, 255, 0.015);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  transition:
    transform var(--transition-standard),
    border-color var(--transition-standard),
    background var(--transition-standard),
    box-shadow var(--transition-standard);
=======
  grid-template-columns: minmax(140px, 210px) minmax(0, 1.4fr) minmax(0, 1fr) minmax(150px, 220px);
  gap: 0.75rem 1rem;
  align-items: start;
  padding: 1rem;
  transition: border-color var(--duration-fast) var(--ease-out), transform var(--duration-fast) var(--ease-out);
>>>>>>> f42ff6b (Changes)
}

.projectCard:hover,
.projectCard:focus-within {
<<<<<<< HEAD
  transform: translateY(-3px);
  border-color: rgba(214, 224, 236, 0.1);
  box-shadow:
    0 16px 28px rgba(4, 8, 14, 0.12),
    inset 0 1px 0 rgba(255, 255, 255, 0.02);
}

.projectCard__top {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 0.55rem 0.85rem;
  align-items: center;
}

.projectCard__status {
  color: rgba(192, 211, 232, 0.8);
  font-family: var(--font-accent);
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}

.projectCard__category {
  color: var(--color-text-muted);
  font-size: 0.8rem;
  line-height: 1.5;
  text-align: right;
}

.projectCard__main {
  display: grid;
  gap: 0.7rem;
}

.projectCard__title {
  color: var(--color-text-strong);
  font-family: var(--font-display);
  font-size: 1.4rem;
  line-height: 1.02;
  letter-spacing: -0.02em;
}

.projectCard__summary {
  color: var(--color-text-base);
  font-size: 0.94rem;
  line-height: 1.8;
}

.projectCard__section {
  display: grid;
  gap: 0.65rem;
}

.projectCard__label {
  color: rgba(192, 211, 232, 0.76);
  font-family: var(--font-accent);
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
=======
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
>>>>>>> f42ff6b (Changes)
}

.projectCard__highlights {
  display: grid;
  gap: 0.45rem;
}

.projectCard__highlights li {
  position: relative;
<<<<<<< HEAD
  padding-left: 0.9rem;
  color: var(--color-text-muted);
  font-size: 0.9rem;
  line-height: 1.68;
=======
  padding-left: 0.75rem;
  color: var(--color-ink-dim);
  font-size: 0.83rem;
  line-height: 1.52;
>>>>>>> f42ff6b (Changes)
}

.projectCard__highlights li::before {
  content: '';
  position: absolute;
<<<<<<< HEAD
  top: 0.7rem;
  left: 0;
  width: 0.32rem;
  height: 0.32rem;
  border-radius: 999px;
  background: rgba(192, 211, 232, 0.7);
=======
  left: 0;
  top: 0.5rem;
  width: 0.33rem;
  height: 1px;
  background: var(--color-line-strong);
>>>>>>> f42ff6b (Changes)
}

.projectCard__stack {
  display: flex;
  flex-wrap: wrap;
<<<<<<< HEAD
  gap: 0.42rem;
}

.projectCard__stack li {
  display: inline-flex;
  align-items: center;
  min-height: 1.85rem;
  padding: 0.35rem 0.58rem;
  border: 1px solid rgba(214, 224, 236, 0.05);
  border-radius: 999px;
  background: rgba(223, 232, 242, 0.018);
  color: rgba(219, 228, 238, 0.76);
  font-size: 0.76rem;
  font-weight: 600;
}

.projectCard__links {
  display: flex;
  flex-wrap: wrap;
  gap: 0.65rem;
  align-items: center;
  margin-top: 0.2rem;
}

.projectCard__link {
  position: relative;
  color: var(--color-text-strong);
  font-size: 0.88rem;
  font-weight: 700;
  transition: color var(--transition-standard);
}

.projectCard__link::after {
  content: '';
  position: absolute;
  right: 0;
  bottom: -0.18rem;
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

.projectCard__link:hover,
.projectCard__link:focus-visible {
  color: var(--color-text-strong);
  outline: none;
}

.projectCard__link:hover::after,
.projectCard__link:focus-visible::after {
  opacity: 1;
  transform: scaleX(1);
}

.projectCard__link--muted {
  color: var(--color-text-muted);
}

.projectCard__link--muted::after {
  display: none;
}

@media (max-width: 1080px) {
  .projectCard__title {
    font-size: 1.3rem;
  }
}

@media (max-width: 640px) {
  .projectCard {
    gap: 0.95rem;
    padding: 1.05rem 0.95rem 1rem;
    border-radius: 18px;
  }

  .projectCard__top {
    align-items: start;
  }

  .projectCard__category {
    text-align: left;
  }

  .projectCard__summary,
  .projectCard__highlights li {
    font-size: 0.92rem;
    line-height: 1.72;
  }
}
</style>
=======
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
>>>>>>> f42ff6b (Changes)
