<script setup>
const props = defineProps({
  activeSection: {
    type: String,
    default: 'hero',
  },
})

const navItems = [
  { id: 'hero', label: 'Home' },
  { id: 'about', label: 'About' },
  { id: 'projects', label: 'Projects' },
  { id: 'contact', label: 'Contact' },
]
</script>

<template>
  <header class="siteHeader">
    <div class="siteHeader__inner">
      <a class="siteHeader__brand" href="#hero" aria-label="SomberDesign home">
        <img src="/assets/images/SomberDesignLogo.png" alt="SomberDesign logo" class="siteHeader__logo" />
        <span>SomberDesign</span>
      </a>

      <nav class="siteHeader__nav" aria-label="Primary navigation">
        <a
          v-for="item in navItems"
          :key="item.id"
          :href="`#${item.id}`"
          class="siteHeader__link"
          :aria-current="activeSection === item.id ? 'page' : undefined"
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
  z-index: 20;
  backdrop-filter: blur(8px);
}

.siteHeader__inner {
  width: var(--site-width);
  min-height: var(--header-height);
  margin: 0.6rem auto 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  border: 1px solid var(--color-border);
  background: rgba(14, 21, 30, 0.86);
  padding: 0.45rem 0.7rem;
}

.siteHeader__brand {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.15rem;
  color: var(--color-text-strong);
}

.siteHeader__logo {
  width: 2.6rem;
  height: 2.6rem;
  object-fit: contain;
}

.siteHeader__nav {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.siteHeader__link {
  padding: 0.35rem 0.6rem;
  border: 1px solid transparent;
  font-weight: 700;
  color: var(--color-text-base);
}

.siteHeader__link[aria-current='page'] {
  border-color: var(--color-border);
  background: var(--color-surface-soft);
  color: var(--color-text-strong);
}
</style>
