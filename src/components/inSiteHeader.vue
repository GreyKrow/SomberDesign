<script setup>
import { computed, ref } from 'vue'

const props = defineProps({
  activeSection: {
    type: String,
    default: 'hero',
  },
})

const isMenuOpen = ref(false)

const navItems = [
  { id: 'hero', label: 'Index' },
  { id: 'about', label: 'Approach' },
  { id: 'projects', label: 'Work' },
  { id: 'contact', label: 'Contact' },
]

const shellClasses = computed(() => ({
  isCompact: props.activeSection !== 'hero',
}))

const closeMenu = () => {
  isMenuOpen.value = false
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <header class="siteHeader" :class="shellClasses">
    <div class="shell-grid siteHeader__inner line-frame">
      <a href="#hero" class="siteHeader__brand" aria-label="Somber.Design home" @click="closeMenu">
        <img class="siteHeader__logo" src="/assets/images/SomberDesignLogo.png" alt="Somber.Design logo" />
        <div>
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
          :class="{ isActive: activeSection === item.id }"
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
  z-index: 30;
  padding-top: 0.7rem;
}

.siteHeader__inner {
  position: relative;
  align-items: center;
  min-height: var(--header-height);
  background: rgba(7, 9, 13, 0.86);
  backdrop-filter: blur(8px);
}

.siteHeader__brand {
  grid-column: 1 / span 5;
  display: inline-flex;
  gap: 0.8rem;
  align-items: center;
  padding-left: 1rem;
}

.siteHeader__logo {
  width: 44px;
  height: 44px;
  object-fit: contain;
}

.siteHeader__wordmark {
  font-family: var(--font-display);
  font-size: 1.16rem;
  font-weight: 600;
  letter-spacing: -0.02em;
}

.siteHeader__meta {
  color: var(--color-ink-muted);
  font-family: var(--font-mono);
  font-size: 0.68rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
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
  height: 100%;
  padding: 0 1rem;
  border-left: 1px solid rgba(243, 245, 248, 0.1);
  color: var(--color-ink-dim);
  font-family: var(--font-mono);
  font-size: 0.72rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  transition: color var(--duration-fast) var(--ease-out), background var(--duration-fast) var(--ease-out);
}

.siteHeader__link:hover,
.siteHeader__link:focus-visible,
.siteHeader__link.isActive {
  color: var(--color-ink);
  background: rgba(243, 245, 248, 0.07);
  outline: none;
}

.siteHeader__menuButton {
  display: none;
}

@media (max-width: 900px) {
  .siteHeader__brand {
    grid-column: 1 / span 10;
  }

  .siteHeader__menuButton {
    grid-column: 11 / -1;
    justify-self: end;
    display: grid;
    gap: 0.4rem;
    width: 48px;
    height: 48px;
    border: 0;
    border-left: 1px solid rgba(243, 245, 248, 0.1);
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
    top: calc(100% + 0.55rem);
    right: 0;
    display: grid;
    min-width: min(320px, 100%);
    border: 1px solid var(--color-line);
    background: rgba(7, 9, 13, 0.96);
    opacity: 0;
    pointer-events: none;
    transform: translateY(-8px);
    transition: opacity var(--duration-base) var(--ease-out), transform var(--duration-base) var(--ease-out);
  }

  .siteHeader__nav.isOpen {
    opacity: 1;
    pointer-events: auto;
    transform: translateY(0);
  }

  .siteHeader__link {
    min-height: 48px;
    border-left: 0;
    border-top: 1px solid rgba(243, 245, 248, 0.1);
  }

  .siteHeader__link:first-child {
    border-top: 0;
  }
}
</style>
