<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="siteFooter">
<<<<<<< HEAD
    <div class="siteFooter__inner">
      <div class="siteFooter__main">
        <span class="siteFooter__eyebrow">Closing signal</span>

        <div class="siteFooter__identity">
          <p class="siteFooter__brand">SomberDesign</p>
          <p class="siteFooter__maker">
            Designed and built by
            <span class="siteFooter__makerName">Jacob</span>
          </p>
        </div>

        <p class="siteFooter__note">
          A quiet personal space for selected work, evolving systems, and the
          shape of what is still being built.
        </p>
      </div>

      <div class="siteFooter__meta">
        <div class="siteFooter__navBlock">
          <p class="siteFooter__metaLabel">Sections</p>

          <div class="siteFooter__links">
            <a href="#hero" class="siteFooter__link">Home</a>
            <a href="#about" class="siteFooter__link">About</a>
            <a href="#projects" class="siteFooter__link">Projects</a>
            <a href="#contact" class="siteFooter__link">Contact</a>
          </div>
        </div>

        <p class="siteFooter__copyright">© {{ currentYear }} SomberDesign</p>
      </div>
=======
    <div class="shell-grid siteFooter__inner">
      <p class="siteFooter__brand">Somber.Design</p>
      <p class="siteFooter__note">Quiet archive for websites, frontend systems, personal tools, and identity work.</p>
      <p class="siteFooter__copyright">© {{ currentYear }} · Crafted by Jacob</p>
>>>>>>> f42ff6b (Changes)
    </div>
  </footer>
</template>

<style scoped lang="scss">
.siteFooter {
<<<<<<< HEAD
  position: relative;
  padding: 5rem 0 2rem;
}

.siteFooter__inner {
  display: grid;
  grid-template-columns: minmax(0, 1.45fr) minmax(220px, 0.8fr);
  gap: 2rem;
  width: var(--site-width);
  margin: 0 auto;
  padding-top: 1.5rem;
  border-top: 1px solid rgba(214, 224, 236, 0.1);
}

.siteFooter__main {
  display: grid;
  gap: 1rem;
  min-width: 0;
}

.siteFooter__eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 0.65rem;
  width: fit-content;
  color: rgba(192, 211, 232, 0.78);
  font-family: var(--font-accent);
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.16em;
  text-transform: uppercase;
}

.siteFooter__eyebrow::before {
  content: '';
  display: inline-block;
  width: 1.7rem;
  height: 1px;
  background: currentColor;
  opacity: 0.55;
}

.siteFooter__identity {
  display: grid;
  gap: 0.35rem;
}

.siteFooter__brand {
  color: var(--color-text-strong);
  font-family: var(--font-display);
  font-size: clamp(1.55rem, 2vw, 1.9rem);
  line-height: 0.95;
  letter-spacing: 0.01em;
}

.siteFooter__maker {
  display: inline-flex;
  align-items: baseline;
  gap: 0.45rem;
  color: var(--color-text-muted);
  font-size: 0.88rem;
  line-height: 1.4;
}

.siteFooter__makerName {
  color: rgba(232, 239, 247, 0.88);
  font-family: var(--font-display);
  font-size: 1rem;
  font-style: italic;
  letter-spacing: 0.02em;
}

.siteFooter__note {
  max-width: 42rem;
  color: var(--color-text-muted);
  font-size: 0.95rem;
  line-height: 1.75;
}

.siteFooter__meta {
  display: grid;
  align-content: space-between;
  gap: 1.25rem;
  min-width: 0;
  justify-items: end;
  text-align: right;
}

.siteFooter__navBlock {
  display: grid;
  gap: 0.7rem;
}

.siteFooter__metaLabel {
  color: rgba(192, 211, 232, 0.72);
  font-family: var(--font-accent);
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.16em;
  text-transform: uppercase;
}

.siteFooter__links {
  display: inline-flex;
  flex-wrap: wrap;
  justify-content: flex-end;
  gap: 0.45rem 0.8rem;
}

.siteFooter__link {
  position: relative;
  color: var(--color-text-muted);
  font-size: 0.9rem;
  line-height: 1.5;
  transition: color var(--transition-standard);
}

.siteFooter__link::after {
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
  transform: scaleX(0.7);
  transform-origin: center;
  transition:
    opacity var(--transition-standard),
    transform var(--transition-standard);
}

.siteFooter__link:hover,
.siteFooter__link:focus-visible {
  color: var(--color-text-strong);
  outline: none;
}

.siteFooter__link:hover::after,
.siteFooter__link:focus-visible::after {
  opacity: 1;
  transform: scaleX(1);
}

.siteFooter__copyright {
  color: rgba(159, 171, 185, 0.82);
  font-size: 0.82rem;
  line-height: 1.5;
}

@media (max-width: 860px) {
  .siteFooter {
    padding-top: 4rem;
  }

  .siteFooter__inner {
    grid-template-columns: 1fr;
    gap: 1.8rem;
  }

  .siteFooter__meta {
    justify-items: start;
    text-align: left;
  }

  .siteFooter__links {
    justify-content: flex-start;
  }
}

@media (max-width: 560px) {
  .siteFooter {
    padding-top: 3.5rem;
    padding-bottom: 1.6rem;
  }

  .siteFooter__inner {
    gap: 1.5rem;
    padding-top: 1.2rem;
  }

  .siteFooter__brand {
    font-size: 1.35rem;
  }

  .siteFooter__maker {
    flex-wrap: wrap;
    gap: 0.25rem 0.45rem;
  }

  .siteFooter__note {
    font-size: 0.92rem;
    line-height: 1.7;
=======
  padding: 0.5rem 0 2rem;
}

.siteFooter__inner {
  align-items: center;
  padding-top: 0.85rem;
  border-top: 1px solid rgba(243, 245, 248, 0.16);
}

.siteFooter__brand {
  grid-column: 1 / span 3;
  font-family: var(--font-display);
  font-size: 0.95rem;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}

.siteFooter__note {
  grid-column: 4 / span 6;
  color: var(--color-ink-muted);
  font-size: 0.8rem;
}

.siteFooter__copyright {
  grid-column: 10 / -1;
  justify-self: end;
  color: var(--color-ink-muted);
  font-family: var(--font-mono);
  font-size: 0.64rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}

@media (max-width: 900px) {
  .siteFooter__brand,
  .siteFooter__note,
  .siteFooter__copyright {
    grid-column: 1 / -1;
    justify-self: start;
  }

  .siteFooter__inner {
    gap: 0.4rem;
>>>>>>> f42ff6b (Changes)
  }
}
</style>