<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'

const isMenuOpen = ref(false)

const navItems = [
  { id: 'hero', label: 'Index' },
  { id: 'about', label: 'Approach' },
  { id: 'projects', label: 'Work' },
  { id: 'contact', label: 'Contact' },
]

const closeMenu = () => {
  isMenuOpen.value = false
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const handleResize = () => {
  if (window.innerWidth > 900) {
    closeMenu()
  }
}

const handleKeydown = event => {
  if (event.key === 'Escape') {
    closeMenu()
  }
}

onMounted(() => {
  window.addEventListener('resize', handleResize)
  window.addEventListener('keydown', handleKeydown)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', handleResize)
  window.removeEventListener('keydown', handleKeydown)
})
</script>

<template>
  <header class="siteHeader">
    <div class="shell-grid siteHeader__inner line-frame">
      <a href="#hero" class="siteHeader__brand" aria-label="Somber.Design home" @click="closeMenu">
        <img class="siteHeader__logo" src="/assets/images/SomberDesignLogo.png" alt="Somber.Design logo" />
        <div class="siteHeader__identity">
          <p class="siteHeader__wordmark">Somber.Design</p>
          <p class="siteHeader__meta">Design × Frontend × Systems</p>
        </div>
      </a>

      <button
        class="siteHeader__menuButton"
        :class="{ isOpen: isMenuOpen }"
        type="button"
        aria-label="Toggle navigation"
        aria-controls="site-primary-nav"
        :aria-expanded="isMenuOpen"
        @click="toggleMenu"
      >
        <span></span>
        <span></span>
      </button>

      <nav id="site-primary-nav" class="siteHeader__nav" :class="{ isOpen: isMenuOpen }" aria-label="Primary navigation">
        <a
          v-for="item in navItems"
          :key="item.id"
          :href="`#${item.id}`"
          class="siteHeader__link"
          @click="closeMenu"
        >
          {{ item.label }}
        </a>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss">
.siteHeader {
  position: sticky;
  top: 0;
  z-index: 40;
  padding-top: 0.7rem;
}

.siteHeader__inner {
  position: relative;
  align-items: center;
  min-height: var(--header-height);
  overflow: visible;
  background: rgba(7, 9, 13, 0.88);
  backdrop-filter: blur(8px);
}

.siteHeader__brand {
  grid-column: 1 / span 5;
  display: inline-flex;
  gap: 0.8rem;
  align-items: center;
  min-width: 0;
  padding-left: 1rem;
}

.siteHeader__identity {
  min-width: 0;
}

.siteHeader__logo {
  width: 42px;
  height: 42px;
  object-fit: contain;
  flex-shrink: 0;
}

.siteHeader__wordmark {
  font-family: var(--font-display);
  font-size: 1.08rem;
  font-weight: 600;
  letter-spacing: -0.02em;
}

.siteHeader__meta {
  overflow: hidden;
  color: var(--color-ink-muted);
  font-family: var(--font-mono);
  font-size: 0.65rem;
  letter-spacing: 0.11em;
  text-overflow: ellipsis;
  text-transform: uppercase;
  white-space: nowrap;
}

.siteHeader__nav {
  grid-column: 7 / -1;
  display: inline-flex;
  justify-self: end;
  height: 100%;
}

.siteHeader__link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  min-width: 7.25rem;
  padding: 0 1rem;
  border-left: 1px solid rgba(243, 245, 248, 0.1);
  color: var(--color-ink-dim);
  font-family: var(--font-mono);
  font-size: 0.69rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  transition: color var(--duration-fast) var(--ease-out), background var(--duration-fast) var(--ease-out);
}

.siteHeader__link:hover,
.siteHeader__link:focus-visible {
  color: var(--color-ink);
  background: rgba(243, 245, 248, 0.08);
  outline: none;
}

.siteHeader__menuButton {
  display: none;
}

@media (max-width: 900px) {
  .siteHeader {
    padding-top: 0.45rem;
  }

  .siteHeader__brand {
    grid-column: 1 / span 9;
    padding-left: 0.85rem;
  }

  .siteHeader__meta {
    font-size: 0.61rem;
  }

  .siteHeader__menuButton {
    grid-column: 10 / -1;
    justify-self: end;
    display: grid;
    gap: 0.35rem;
    width: 50px;
    height: 50px;
    border: 0;
    border-left: 1px solid rgba(243, 245, 248, 0.12);
    background: transparent;
    cursor: pointer;
  }

  .siteHeader__menuButton span {
    width: 18px;
    height: 1px;
    margin: auto;
    background: var(--color-ink);
    transform-origin: center;
    transition: transform var(--duration-fast) var(--ease-out), opacity var(--duration-fast) var(--ease-out);
  }

  .siteHeader__menuButton.isOpen span:first-child {
    transform: translateY(3px) rotate(35deg);
  }

  .siteHeader__menuButton.isOpen span:last-child {
    transform: translateY(-3px) rotate(-35deg);
  }

  .siteHeader__nav {
    position: absolute;
    left: 0;
    right: 0;
    top: calc(100% + 0.45rem);
    z-index: 2;
    display: grid;
    border: 1px solid var(--color-line);
    background: rgba(7, 9, 13, 0.98);
    opacity: 0;
    pointer-events: none;
    transform: translateY(-6px);
    transition: opacity var(--duration-base) var(--ease-out), transform var(--duration-base) var(--ease-out);
  }

  .siteHeader__nav.isOpen {
    opacity: 1;
    pointer-events: auto;
    transform: translateY(0);
  }

  .siteHeader__link {
    min-height: 50px;
    min-width: 0;
    justify-content: flex-start;
    border-left: 0;
    border-top: 1px solid rgba(243, 245, 248, 0.12);
    padding-inline: 0.95rem;
  }

  .siteHeader__link:first-child {
    border-top: 0;
  }
}

@media (max-width: 560px) {
  .siteHeader__brand {
    grid-column: 1 / span 8;
    gap: 0.6rem;
  }

  .siteHeader__logo {
    width: 36px;
    height: 36px;
  }

  .siteHeader__wordmark {
    font-size: 0.94rem;
  }

  .siteHeader__meta {
    max-width: 22ch;
  }

  .siteHeader__menuButton {
    grid-column: 9 / -1;
  }
}
</style>
