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
    <p class="projectCard__status">{{ props.project.status }} / {{ props.project.category }}</p>
    <h3 class="projectCard__title">{{ props.project.title }}</h3>
    <p class="projectCard__summary">{{ props.project.summary }}</p>

    <ul class="projectCard__highlights">
      <li v-for="highlight in props.project.highlights" :key="highlight">{{ highlight }}</li>
    </ul>

    <ul class="projectCard__stack">
      <li v-for="tech in props.project.stack" :key="tech">{{ tech }}</li>
    </ul>

    <div class="projectCard__links">
      <template v-if="props.project.links.length">
        <a
          v-for="link in props.project.links.filter(item => item.href)"
          :key="link.label"
          :href="link.href"
          target="_blank"
          rel="noreferrer"
        >
          {{ link.label }}
        </a>
      </template>
      <span v-else>Private work</span>
    </div>
  </article>
</template>

<style scoped lang="scss">
.projectCard {
  border: 1px solid var(--color-border);
  background: var(--color-surface-soft);
  padding: 1rem;
  display: grid;
  gap: 0.8rem;
}

.projectCard__status {
  font-size: 0.78rem;
  font-weight: 800;
  text-transform: uppercase;
  color: var(--color-accent);
}

.projectCard__title {
  font-family: var(--font-display);
  font-size: 1.4rem;
  line-height: 1.1;
  color: var(--color-text-strong);
}

.projectCard__highlights {
  list-style: disc;
  padding-left: 1.2rem;
  display: grid;
  gap: 0.35rem;
}

.projectCard__stack {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  gap: 0.45rem;
}

.projectCard__stack li {
  border: 1px solid var(--color-border);
  padding: 0.18rem 0.45rem;
  font-size: 0.8rem;
}

.projectCard__links {
  color: var(--color-text-muted);
}

.projectCard__links a {
  display: inline-block;
  margin-right: 0.8rem;
  margin-top: 0.2rem;
  padding-bottom: 0.1rem;
  border-bottom: 1px solid var(--color-border);
  font-weight: 700;
  color: var(--color-text-strong);
}
</style>
