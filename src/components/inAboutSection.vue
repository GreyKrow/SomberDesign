<script setup>
import { profileData } from '../data/inProfileData'

const aboutNotes = [
  {
    label: 'What I build',
    text: 'Personal tools, identity-led websites, and smaller digital systems that feel useful, intentional, and worth keeping around.',
  },
  {
    label: 'How I work',
    text: 'I prefer compact builds with clear structure, restrained presentation, and visual decisions that support the feeling of the work instead of overpowering it.',
  },
  {
    label: 'Why this site exists',
    text: 'SomberDesign is where I keep a record of the work that actually matters to me — finished projects, evolving ideas, and unfinished pieces that still belong to the archive.',
  },
]
</script>

<template>
  <section class="aboutSection" id="about">
    <div class="aboutSection__inner">
      <div class="aboutSection__intro">
        <div class="aboutSection__introMain">
          <p class="eyebrow">About</p>
          <h2 class="aboutSection__title">
            A quieter place to keep the work that matters.
          </h2>
          <p class="aboutSection__text">
            {{ profileData.summary }}
          </p>
        </div>

        <aside class="aboutSection__principlesBlock">
          <p class="aboutSection__principlesLabel">What matters here</p>

          <ul class="aboutSection__principles">
            <li v-for="principle in profileData.principles" :key="principle">
              {{ principle }}
            </li>
          </ul>
        </aside>
      </div>

      <div class="aboutSection__notes">
        <article
          v-for="note in aboutNotes"
          :key="note.label"
          class="aboutSection__note"
        >
          <p class="aboutSection__noteLabel">{{ note.label }}</p>
          <p class="aboutSection__noteText">{{ note.text }}</p>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.aboutSection {
  padding: 1.2rem 0 0;
}

.aboutSection__inner {
  display: grid;
  gap: 2rem;
  width: var(--site-width);
  margin: 0 auto;
}

.aboutSection__intro {
  display: grid;
  grid-template-columns: minmax(0, 1.15fr) minmax(260px, 0.7fr);
  gap: 1.5rem;
  align-items: start;
  padding: 1.6rem 0 0;
  border-top: 1px solid rgba(214, 224, 236, 0.08);
}

.aboutSection__introMain {
  max-width: 38rem;
}

.aboutSection__title {
  max-width: 20ch;
  margin-top: 0.9rem;
  color: var(--color-text-strong);
  font-family: var(--font-display);
  font-size: clamp(1.65rem, 3vw, 2.5rem);
  line-height: 1.08;
  letter-spacing: -0.025em;
  text-wrap: balance;
}

.aboutSection__text {
  max-width: 34rem;
  margin-top: 1rem;
  color: var(--color-text-base);
  font-size: 0.98rem;
  line-height: 1.85;
}

.aboutSection__principlesBlock {
  padding: 1rem 1rem 1.05rem;
  border: 1px solid rgba(214, 224, 236, 0.06);
  border-radius: 18px;
  background:
    linear-gradient(180deg, rgba(21, 28, 36, 0.56), rgba(15, 20, 27, 0.62)),
    rgba(10, 15, 22, 0.12);
  box-shadow:
    0 10px 22px rgba(4, 8, 14, 0.08),
    inset 0 1px 0 rgba(255, 255, 255, 0.015);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
}

.aboutSection__principlesLabel {
  color: rgba(192, 211, 232, 0.78);
  font-family: var(--font-accent);
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}

.aboutSection__principles {
  display: grid;
  gap: 0.8rem;
  margin-top: 0.95rem;
}

.aboutSection__principles li {
  position: relative;
  padding-left: 1rem;
  color: var(--color-text-muted);
  font-size: 0.92rem;
  line-height: 1.7;
}

.aboutSection__principles li::before {
  content: '';
  position: absolute;
  top: 0.72rem;
  left: 0;
  width: 0.38rem;
  height: 0.38rem;
  border-radius: 999px;
  background: rgba(192, 211, 232, 0.72);
}

.aboutSection__notes {
  display: grid;
  gap: 0;
  border-top: 1px solid rgba(214, 224, 236, 0.08);
}

.aboutSection__note {
  display: grid;
  grid-template-columns: minmax(180px, 220px) minmax(0, 1fr);
  gap: 1.25rem;
  padding: 1.15rem 0;
  border-bottom: 1px solid rgba(214, 224, 236, 0.08);
}

.aboutSection__noteLabel {
  color: var(--color-text-strong);
  font-family: var(--font-accent);
  font-size: 0.76rem;
  font-weight: 700;
  letter-spacing: 0.13em;
  text-transform: uppercase;
}

.aboutSection__noteText {
  max-width: 44rem;
  color: var(--color-text-muted);
  font-size: 0.96rem;
  line-height: 1.8;
}

@media (max-width: 900px) {
  .aboutSection__intro {
    grid-template-columns: 1fr;
    gap: 1.2rem;
  }

  .aboutSection__principlesBlock {
    max-width: 32rem;
  }

  .aboutSection__note {
    grid-template-columns: 1fr;
    gap: 0.55rem;
  }
}

@media (max-width: 640px) {
  .aboutSection {
    padding-top: 0.8rem;
  }

  .aboutSection__inner {
    gap: 1.5rem;
  }

  .aboutSection__intro {
    padding-top: 1.2rem;
  }

  .aboutSection__title {
    font-size: clamp(1.45rem, 7vw, 2rem);
    line-height: 1.12;
  }

  .aboutSection__text,
  .aboutSection__noteText {
    font-size: 0.94rem;
    line-height: 1.75;
  }

  .aboutSection__principlesBlock {
    padding: 0.95rem 0.95rem 1rem;
    border-radius: 16px;
  }

  .aboutSection__note {
    padding: 1rem 0;
  }
}
</style>