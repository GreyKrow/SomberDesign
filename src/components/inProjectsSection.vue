<script setup>
import { projectsData } from '../data/inProjectsData'
import inProjectCard from './inProjectCard.vue'
</script>

<template>
  <section class="projectsSection" id="projects" aria-labelledby="projects-title">
    <p class="eyebrow">Projects</p>
    <h2 id="projects-title" class="projectsSection__title">Recent work</h2>
    <p class="projectsSection__text">A focused set of practical builds with clear outcomes.</p>

    <div class="projectsSection__grid">
      <inProjectCard v-for="project in projectsData" :key="project.title" :project="project" />
    </div>
  </section>
</template>

<style scoped lang="scss">
.projectsSection {
  padding: 2rem 0;
  border-bottom: 3px solid var(--color-border);
}

.projectsSection__title {
  margin-top: 0.9rem;
  font-family: var(--font-display);
  font-size: clamp(1.6rem, 5vw, 2.4rem);
}

.projectsSection__text {
  margin-top: 0.8rem;
}

.projectsSection__grid {
  margin-top: 1rem;
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(3, minmax(0, 1fr));
}

@media (max-width: 960px) {
  .projectsSection__grid {
    grid-template-columns: 1fr;
  }
}
</style>
