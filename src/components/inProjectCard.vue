<script setup>
const props = defineProps({
  project: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <article class="projectCard">
    <div class="projectCard__top">
      <p class="projectCard__status">{{ props.project.status }}</p>
      <p class="projectCard__category">{{ props.project.category }}</p>
    </div>

    <div class="projectCard__main">
      <h3 class="projectCard__title">{{ props.project.title }}</h3>
      <p class="projectCard__summary">{{ props.project.summary }}</p>
    </div>

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
    </div>

    <div class="projectCard__links">
      <template v-for="link in props.project.links" :key="link.label">
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
      </template>
    </div>
  </article>
</template>

<style scoped lang="scss">
.projectCard {
  display: grid;
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
}

.projectCard:hover,
.projectCard:focus-within {
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
}

.projectCard__highlights {
  display: grid;
  gap: 0.45rem;
}

.projectCard__highlights li {
  position: relative;
  padding-left: 0.9rem;
  color: var(--color-text-muted);
  font-size: 0.9rem;
  line-height: 1.68;
}

.projectCard__highlights li::before {
  content: '';
  position: absolute;
  top: 0.7rem;
  left: 0;
  width: 0.32rem;
  height: 0.32rem;
  border-radius: 999px;
  background: rgba(192, 211, 232, 0.7);
}

.projectCard__stack {
  display: flex;
  flex-wrap: wrap;
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
