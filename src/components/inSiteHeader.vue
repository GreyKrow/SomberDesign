<script setup>
<<<<<<< HEAD
import { computed, ref } from 'vue'

const props = defineProps({
  activeSection: {
    type: String,
    default: 'hero',
  },
})
=======
import { onBeforeUnmount, onMounted, ref } from 'vue'
>>>>>>> f42ff6b (Changes)

const isMenuOpen = ref(false)

const navItems = [
<<<<<<< HEAD
  { id: 'hero', label: 'Home' },
  { id: 'about', label: 'About' },
  { id: 'projects', label: 'Projects' },
  { id: 'contact', label: 'Contact' },
]

const shellClasses = computed(() => ({
  isCompact: props.activeSection !== 'hero',
}))

=======
  { id: 'hero', label: 'Index' },
  { id: 'about', label: 'Approach' },
  { id: 'projects', label: 'Work' },
  { id: 'contact', label: 'Contact' },
]

>>>>>>> f42ff6b (Changes)
const closeMenu = () => {
  isMenuOpen.value = false
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
<<<<<<< HEAD
</script>

<template>
  <header class="siteHeader" :class="shellClasses">
    <div class="siteHeader__inner">
      <div class="siteHeader__brand" aria-label="SomberDesign identity">
        <img
          class="siteHeader__logo"
          src="/assets/images/SomberDesignLogo.png"
          alt="SomberDesign logo"
        />

        <span class="siteHeader__brandText">
          <span class="siteHeader__wordmark">SomberDesign</span>

          <span class="siteHeader__signature">
            <span class="siteHeader__signatureLine" aria-hidden="true"></span>
            <span class="siteHeader__signatureName">Jacob</span>
          </span>
        </span>
      </div>
=======

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
>>>>>>> f42ff6b (Changes)

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
<<<<<<< HEAD
        <span></span>
      </button>

      <nav
        id="site-primary-nav"
        class="siteHeader__nav"
        :class="{ isOpen: isMenuOpen }"
        aria-label="Primary navigation"
      >
=======
      </button>

      <nav id="site-primary-nav" class="siteHeader__nav" :class="{ isOpen: isMenuOpen }" aria-label="Primary navigation">
>>>>>>> f42ff6b (Changes)
        <a
          v-for="item in navItems"
          :key="item.id"
          :href="`#${item.id}`"
          class="siteHeader__link"
<<<<<<< HEAD
          :class="{ isActive: activeSection === item.id }"
=======
>>>>>>> f42ff6b (Changes)
          @click="closeMenu"
        >
          {{ item.label }}
        </a>
      </nav>
    </div>
<<<<<<< HEAD
=======

    <button
      v-if="isMenuOpen"
      class="siteHeader__scrim"
      type="button"
      aria-label="Close navigation menu"
      @click="closeMenu"
    ></button>
>>>>>>> f42ff6b (Changes)
  </header>
</template>

<style scoped lang="scss">
.siteHeader {
  position: sticky;
  top: 0;
<<<<<<< HEAD
  z-index: 20;
  padding: 0.7rem 0 0;
  transition: padding-top var(--transition-standard);
}

.siteHeader.isCompact {
=======
  z-index: 80;
>>>>>>> f42ff6b (Changes)
  padding-top: 0.7rem;
}

.siteHeader__inner {
  position: relative;
<<<<<<< HEAD
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1.5rem;
  width: var(--site-width);
  margin: 0 auto;
  padding: 0.86rem 1rem;
  border: 1px solid rgba(214, 224, 236, 0.08);
  border-radius: 20px;
  background:
    linear-gradient(180deg, rgba(15, 21, 29, 0.88), rgba(12, 17, 24, 0.82)),
    rgba(9, 13, 19, 0.45);
  box-shadow:
    0 14px 32px rgba(4, 8, 14, 0.18),
    inset 0 1px 0 rgba(255, 255, 255, 0.02);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  transition:
    background var(--transition-standard),
    border-color var(--transition-standard),
    box-shadow var(--transition-standard),
    padding var(--transition-standard);
}

.siteHeader.isCompact .siteHeader__inner {
  padding: 0.86rem 1rem;
  border-color: rgba(214, 224, 236, 0.08);
  background:
    linear-gradient(180deg, rgba(15, 21, 29, 0.88), rgba(12, 17, 24, 0.82)),
    rgba(9, 13, 19, 0.45);
  box-shadow:
    0 14px 32px rgba(4, 8, 14, 0.18),
    inset 0 1px 0 rgba(255, 255, 255, 0.02);
}

.siteHeader__brand {
  display: inline-flex;
  align-items: center;
  gap: 0.8rem;
  min-width: 0;
  flex-shrink: 0;
}

.siteHeader__logo {
  width: auto;
  height: 4.5rem;
  flex-shrink: 0;
  object-fit: contain;
  object-position: center;
  opacity: 0.98;
  filter:
    drop-shadow(0 0 20px rgba(192, 211, 232, 0.14))
    drop-shadow(0 0 2px rgba(255, 255, 255, 0.08));
  transition:
    height var(--transition-standard),
    filter var(--transition-standard),
    opacity var(--transition-standard);
}

.siteHeader.isCompact .siteHeader__logo {
  height: 4.5rem;
}

.siteHeader__brandText {
  display: grid;
  gap: 0.18rem;
  min-width: 0;
}

.siteHeader__wordmark {
  color: var(--color-text-strong);
  font-family: var(--font-display);
  font-size: 1.34rem;
  line-height: 1;
  letter-spacing: 0.01em;
  white-space: nowrap;
}

.siteHeader__signature {
  display: inline-flex;
  align-items: center;
  gap: 0.55rem;
  min-width: 0;
}

.siteHeader__signatureLine {
  display: inline-block;
  width: 1.4rem;
  height: 1px;
  background: linear-gradient(
    90deg,
    rgba(192, 211, 232, 0.15),
    rgba(192, 211, 232, 0.55)
  );
  flex-shrink: 0;
}

.siteHeader__signatureName {
  color: rgba(219, 228, 238, 0.84);
  font-family: var(--font-display);
  font-size: 0.9rem;
  font-style: italic;
  line-height: 1;
  letter-spacing: 0.02em;
  white-space: nowrap;
  opacity: 0.92;
}

.siteHeader__nav {
  display: inline-flex;
  align-items: center;
  justify-content: flex-end;
  gap: 0.2rem;
  min-width: 0;
}

.siteHeader__link {
  position: relative;
  display: inline-flex;
  align-items: center;
  min-height: 2.75rem;
  padding: 0.5rem 0.85rem;
  color: var(--color-text-muted);
  font-size: 0.92rem;
  font-weight: 600;
  letter-spacing: 0.01em;
  transition:
    color var(--transition-standard),
    opacity var(--transition-standard);
}

.siteHeader__link::after {
  content: '';
  position: absolute;
  right: 0.85rem;
  bottom: 0.45rem;
  left: 0.85rem;
  height: 1px;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(192, 211, 232, 0.82),
    transparent
  );
  opacity: 0;
  transform: scaleX(0.7);
  transform-origin: center;
  transition:
    opacity var(--transition-standard),
    transform var(--transition-standard);
=======
  z-index: 2;
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
>>>>>>> f42ff6b (Changes)
}

.siteHeader__link:hover,
.siteHeader__link:focus-visible {
<<<<<<< HEAD
  color: var(--color-text-strong);
  outline: none;
}

.siteHeader__link:hover::after,
.siteHeader__link:focus-visible::after,
.siteHeader__link.isActive::after {
  opacity: 1;
  transform: scaleX(1);
}

.siteHeader__link.isActive {
  color: var(--color-text-strong);
}

.siteHeader__menuButton {
  display: none;
  position: relative;
  width: 2.85rem;
  height: 2.85rem;
  padding: 0;
  border: 1px solid rgba(214, 224, 236, 0.08);
  border-radius: 14px;
  background: rgba(223, 232, 242, 0.03);
  color: var(--color-text-strong);
  cursor: pointer;
  transition:
    background var(--transition-standard),
    border-color var(--transition-standard);
}

.siteHeader__menuButton:hover,
.siteHeader__menuButton:focus-visible {
  background: rgba(223, 232, 242, 0.06);
  border-color: rgba(214, 224, 236, 0.14);
  outline: none;
}

.siteHeader__menuButton span {
  position: absolute;
  left: 50%;
  width: 1.05rem;
  height: 1px;
  border-radius: 999px;
  background: currentColor;
  transform: translateX(-50%);
  transition:
    transform var(--transition-standard),
    opacity var(--transition-standard),
    top var(--transition-standard);
}

.siteHeader__menuButton span:nth-child(1) {
  top: 0.92rem;
}

.siteHeader__menuButton span:nth-child(2) {
  top: 1.38rem;
}

.siteHeader__menuButton span:nth-child(3) {
  top: 1.84rem;
}

.siteHeader__menuButton.isOpen span:nth-child(1) {
  top: 1.38rem;
  transform: translateX(-50%) rotate(45deg);
}

.siteHeader__menuButton.isOpen span:nth-child(2) {
  opacity: 0;
}

.siteHeader__menuButton.isOpen span:nth-child(3) {
  top: 1.38rem;
  transform: translateX(-50%) rotate(-45deg);
}

@media (max-width: 920px) {
  .siteHeader__inner {
    gap: 1rem;
  }

  .siteHeader__menuButton {
    display: inline-block;
    flex-shrink: 0;
=======
  color: var(--color-ink);
  background: rgba(243, 245, 248, 0.08);
  outline: none;
}

.siteHeader__menuButton,
.siteHeader__scrim {
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
    position: relative;
    z-index: 7;
    grid-column: 10 / -1;
    justify-self: end;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    border: 0;
    border-left: 1px solid rgba(243, 245, 248, 0.12);
    background: transparent;
    cursor: pointer;
  }

  .siteHeader__menuButton span {
    position: absolute;
    width: 18px;
    height: 1px;
    background: var(--color-ink);
    transform-origin: center;
    transition: transform var(--duration-fast) var(--ease-out), opacity var(--duration-fast) var(--ease-out);
  }

  .siteHeader__menuButton span:first-child {
    transform: translateY(-4px);
  }

  .siteHeader__menuButton span:last-child {
    transform: translateY(4px);
  }

  .siteHeader__menuButton.isOpen span:first-child {
    transform: rotate(35deg);
  }

  .siteHeader__menuButton.isOpen span:last-child {
    transform: rotate(-35deg);
  }

  .siteHeader__scrim {
    position: fixed;
    inset: 0;
    z-index: 1;
    display: block;
    border: 0;
    background: rgba(4, 6, 9, 0.16);
    cursor: pointer;
>>>>>>> f42ff6b (Changes)
  }

  .siteHeader__nav {
    position: absolute;
<<<<<<< HEAD
    top: calc(100% + 0.7rem);
    right: 0;
    left: 0;
    display: grid;
    gap: 0.15rem;
    padding: 0.6rem;
    border: 1px solid rgba(214, 224, 236, 0.08);
    border-radius: 18px;
    background:
      linear-gradient(180deg, rgba(15, 21, 29, 0.96), rgba(10, 15, 22, 0.94));
    box-shadow: 0 20px 40px rgba(3, 7, 12, 0.28);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    opacity: 0;
    visibility: hidden;
    transform: translateY(-8px);
    transition:
      opacity var(--transition-standard),
      transform var(--transition-standard),
      visibility var(--transition-standard);
=======
    top: calc(100% + 0.45rem);
    right: 0;
    z-index: 6;
    display: grid;
    align-content: start;
    width: min(22rem, calc(100vw - 1.6rem));
    height: auto;
    max-height: calc(100vh - var(--header-height) - 1.5rem);
    overflow-y: auto;
    border: 1px solid var(--color-line);
    background:
      linear-gradient(180deg, rgba(13, 17, 23, 0.98), rgba(7, 9, 13, 0.95)),
      rgba(7, 9, 13, 0.96);
    box-shadow: 0 1.2rem 3rem rgba(0, 0, 0, 0.34);
    backdrop-filter: blur(14px);
    opacity: 0;
    pointer-events: none;
    transform: translate3d(0, -0.4rem, 0) scale(0.985);
    transform-origin: top right;
    visibility: hidden;
    transition:
      opacity var(--duration-base) var(--ease-out),
      transform var(--duration-base) var(--ease-out),
      visibility 0s linear var(--duration-base);
>>>>>>> f42ff6b (Changes)
  }

  .siteHeader__nav.isOpen {
    opacity: 1;
<<<<<<< HEAD
    visibility: visible;
    transform: translateY(0);
  }

  .siteHeader__link {
    width: 100%;
    min-height: 3rem;
    padding: 0.8rem 0.95rem;
    border-radius: 12px;
  }

  .siteHeader__link:hover,
  .siteHeader__link:focus-visible,
  .siteHeader__link.isActive {
    background: rgba(223, 232, 242, 0.04);
  }

  .siteHeader__link::after {
    right: 0.95rem;
    left: 0.95rem;
    bottom: 0.6rem;
  }
}

@media (max-width: 640px) {
  .siteHeader__logo {
    height: 3.8rem;
  }

  .siteHeader.isCompact .siteHeader__logo {
    height: 3.8rem;
  }

  .siteHeader__wordmark {
    font-size: 1.12rem;
  }

  .siteHeader__signatureName {
    font-size: 0.8rem;
  }

  .siteHeader__signatureLine {
    width: 1rem;
=======
    pointer-events: auto;
    transform: translate3d(0, 0, 0) scale(1);
    visibility: visible;
    transition-delay: 0s;
  }

  .siteHeader__link {
    justify-content: space-between;
    width: 100%;
    min-height: 58px;
    min-width: 0;
    border-left: 0;
    border-top: 1px solid rgba(243, 245, 248, 0.12);
    padding-inline: 1rem;
    font-size: 0.72rem;
  }

  .siteHeader__link::after {
    content: '↘';
    color: var(--color-ink-muted);
    font-size: 0.72rem;
    line-height: 1;
    transform: translateY(-1px);
  }

  .siteHeader__link:first-child {
    border-top: 0;
>>>>>>> f42ff6b (Changes)
  }
}

@media (max-width: 560px) {
<<<<<<< HEAD
  .siteHeader {
    padding-top: 0.65rem;
  }

  .siteHeader__inner {
    padding: 0.82rem 0.85rem;
    border-radius: 18px;
  }

  .siteHeader__brand {
    gap: 0.72rem;
  }

  .siteHeader__logo {
    height: 3.35rem;
  }

  .siteHeader.isCompact .siteHeader__logo {
    height: 3.35rem;
  }

  .siteHeader__wordmark {
    font-size: 1rem;
  }

  .siteHeader__signatureName {
    font-size: 0.74rem;
=======
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

  .siteHeader__nav {
    left: 0;
    right: 0;
    width: auto;
    transform-origin: top center;
>>>>>>> f42ff6b (Changes)
  }
}
</style>