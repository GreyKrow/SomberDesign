<script setup>
import { projectsData } from '../data/inProjectsData'
import inProjectCard from './inProjectCard.vue'
</script>

<template>
<<<<<<< HEAD
  <section class="projectsSection" id="projects">
    <div class="projectsSection__inner">
      <div class="projectsSection__copy">
        <p class="eyebrow">Projects</p>
        <h2 class="projectsSection__title">
          Selected work, active builds, and projects still taking shape.
        </h2>
        <p class="projectsSection__text">
          I keep unfinished work visible when it still says something useful.
          This section holds the projects that matter enough to keep refining,
          not just the ones that are perfectly wrapped up.
        </p>
      </div>

      <div class="projectsSection__grid">
        <inProjectCard
          v-for="project in projectsData"
          :key="project.title"
          :project="project"
        />
=======
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
>>>>>>> f42ff6b (Changes)
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.projectsSection {
<<<<<<< HEAD
  padding: 2rem 0 0;
}

.projectsSection__inner {
  display: grid;
  gap: 1.65rem;
  width: var(--site-width);
  margin: 0 auto;
}

.projectsSection__copy {
  max-width: 40rem;
}

.projectsSection__title {
  max-width: 18ch;
  margin-top: 0.9rem;
  color: var(--color-text-strong);
  font-family: var(--font-display);
  font-size: clamp(1.65rem, 3vw, 2.35rem);
  line-height: 1.08;
  letter-spacing: -0.025em;
  text-wrap: balance;
}

.projectsSection__text {
  max-width: 35rem;
  margin-top: 1rem;
  color: var(--color-text-base);
  font-size: 0.98rem;
  line-height: 1.82;
}

.projectsSection__grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 1rem;
  align-items: stretch;
}

@media (max-width: 1080px) {
  .projectsSection__grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 720px) {
  .projectsSection__grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 640px) {
  .projectsSection {
    padding-top: 1.7rem;
  }

  .projectsSection__inner {
    gap: 1.35rem;
  }

  .projectsSection__title {
    font-size: clamp(1.45rem, 7vw, 1.95rem);
    line-height: 1.12;
  }

  .projectsSection__text {
    font-size: 0.94rem;
    line-height: 1.75;
=======
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
>>>>>>> f42ff6b (Changes)
  }
}
</style>