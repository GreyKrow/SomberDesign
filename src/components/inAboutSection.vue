<script setup>
import { profileData } from '../data/inProfileData'

const aboutNotes = [
  {
    title: 'Discipline',
    detail: 'Type, spacing, and rhythm drive the structure before color or ornament.',
  },
  {
    title: 'Output',
    detail: 'Product surfaces, branded websites, and experiments that stay usable under pressure.',
  },
  {
    title: 'Method',
    detail: 'Ship the smallest strong version first, then tighten motion, pacing, and edge cases.',
  },
]
</script>

<template>
  <section class="aboutSection">
    <div class="shell-grid aboutSection__inner">
      <header class="aboutSection__intro">
        <p class="kicker">Approach</p>
        <h2 class="section-title">Built for signal, not spectacle.</h2>
        <p class="section-body">{{ profileData.summary }}</p>
      </header>

      <aside class="aboutSection__principles line-frame" aria-label="Core principles">
        <p class="aboutSection__panelLabel">Rules of engagement</p>
        <ul>
          <li v-for="principle in profileData.principles" :key="principle">{{ principle }}</li>
        </ul>
      </aside>

      <div class="aboutSection__notes">
        <article v-for="note in aboutNotes" :key="note.title" class="aboutSection__note">
          <p class="aboutSection__noteTitle">{{ note.title }}</p>
          <p class="aboutSection__noteBody">{{ note.detail }}</p>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.aboutSection {
  padding: var(--section-pad-y) 0;
}

.aboutSection__intro {
  grid-column: 1 / span 7;
  display: grid;
  gap: 1rem;
}

.aboutSection__principles {
  grid-column: 8 / -1;
  padding: 1rem;
}

.aboutSection__panelLabel {
  margin-bottom: 0.7rem;
  color: var(--color-ink-muted);
  font-family: var(--font-mono);
  font-size: 0.66rem;
  letter-spacing: 0.16em;
  text-transform: uppercase;
}

.aboutSection__principles ul {
  display: grid;
  gap: 0.75rem;
}

.aboutSection__principles li {
  padding-top: 0.7rem;
  border-top: 1px solid rgba(243, 245, 248, 0.1);
  color: var(--color-ink-dim);
  font-size: 0.92rem;
  line-height: 1.66;
}

.aboutSection__notes {
  grid-column: 1 / -1;
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  border-top: 1px solid rgba(243, 245, 248, 0.12);
}

.aboutSection__note {
  min-height: 140px;
  padding: 1rem;
  border-right: 1px solid rgba(243, 245, 248, 0.12);
}

.aboutSection__note:last-child {
  border-right: 0;
}

.aboutSection__noteTitle {
  color: var(--color-ink);
  font-family: var(--font-mono);
  font-size: 0.67rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.aboutSection__noteBody {
  margin-top: 0.75rem;
  color: var(--color-ink-dim);
  font-size: 0.93rem;
  line-height: 1.64;
}

@media (max-width: 900px) {
  .aboutSection__intro,
  .aboutSection__principles {
    grid-column: 1 / -1;
  }

  .aboutSection__notes {
    grid-template-columns: 1fr;
  }

  .aboutSection__note {
    min-height: 0;
    border-right: 0;
    border-top: 1px solid rgba(243, 245, 248, 0.12);
  }
}
</style>
