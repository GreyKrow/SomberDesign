<script setup>
import { projectsData } from '../data/inProjectsData'
import inProjectCard from './inProjectCard.vue'
</script>

<template>
  <section class="projectsSection">
    <div class="shell-grid projectsSection__inner">
      <header class="projectsSection__intro">
        <p class="kicker">Selected Work</p>
        <h2 class="section-title">A small archive of real builds, active experiments, and systems in motion.</h2>
        <p class="section-body">
          The work here is intentionally limited. Finished projects, rough prototypes, and evolving tools all belong
          when they show direction, taste, or useful structure.
        </p>
      </header>

      <div class="projectsSection__rail">
        <inProjectCard v-for="project in projectsData" :key="project.title" :project="project" />
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.projectsSection {
  padding: var(--section-pad-y) 0;
}

.projectsSection__intro {
  grid-column: 1 / span 8;
  display: grid;
  gap: 1rem;
}

.projectsSection__rail {
  grid-column: 1 / -1;
  display: grid;
  gap: 0.8rem;
}

@media (max-width: 900px) {
  .projectsSection__intro {
    grid-column: 1 / -1;
  }
}
</style>
