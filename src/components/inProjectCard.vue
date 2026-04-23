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

    <div class="projectCard__links">
      <a v-for="link in props.project.links.filter(item => item.href)" :key="link.label" :href="link.href" target="_blank" rel="noreferrer">{{ link.label }}</a>
    </div>
  </article>
</template>

<style scoped lang="scss">
.projectCard {
  border: 3px solid var(--color-border);
  background: var(--color-surface);
  padding: 1rem;
  display: grid;
  gap: 0.8rem;
}

.projectCard__status {
  font-size: 0.78rem;
  font-weight: 800;
  text-transform: uppercase;
}

.projectCard__title {
  font-family: var(--font-display);
  font-size: 1.4rem;
  line-height: 1.1;
}

.projectCard__highlights {
  list-style: disc;
  padding-left: 1.2rem;
  display: grid;
  gap: 0.35rem;
}

.projectCard__links a {
  display: inline-block;
  margin-right: 0.8rem;
  margin-top: 0.2rem;
  padding-bottom: 0.1rem;
  border-bottom: 2px solid var(--color-border);
  font-weight: 700;
}
</style>
