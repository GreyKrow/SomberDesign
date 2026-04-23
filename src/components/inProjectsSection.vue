<script setup>
import { projectsData } from '../data/inProjectsData'
import inProjectCard from './inProjectCard.vue'
</script>

<template>
  <section class="projectsSection" id="projects" aria-labelledby="projects-title">
    <p class="eyebrow">Projects</p>
    <h2 id="projects-title" class="projectsSection__title">Selected projects</h2>
    <p class="projectsSection__text">Active builds and ongoing experiments.</p>

    <div class="projectsSection__grid">
      <inProjectCard v-for="project in projectsData" :key="project.title" :project="project" />
    </div>
  </section>
</template>

<style scoped lang="scss">
.projectsSection {
  margin-top: 1rem;
  padding: 1.8rem 1.2rem;
  border: 1px solid var(--color-border);
  border-radius: var(--radius-medium);
  background: var(--color-surface);
}

.projectsSection__title {
  margin-top: 0.8rem;
  font-family: var(--font-display);
  font-size: clamp(1.55rem, 5vw, 2.2rem);
  color: var(--color-text-strong);
}

.projectsSection__text {
  margin-top: 0.7rem;
}

.projectsSection__grid {
  margin-top: 1rem;
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(3, minmax(0, 1fr));
}

@media (max-width: 1024px) {
  .projectsSection__grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 700px) {
  .projectsSection__grid {
    grid-template-columns: 1fr;
  }
}
</style>
