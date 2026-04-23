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
      <a class="siteHeader__brand" href="#hero">SomberDesign</a>

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
  background: var(--color-background);
  border-bottom: 3px solid var(--color-border);
}

.siteHeader__inner {
  width: var(--site-width);
  min-height: var(--header-height);
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}

.siteHeader__brand {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.4rem;
  letter-spacing: 0.01em;
}

.siteHeader__nav {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.siteHeader__link {
  padding: 0.3rem 0.55rem;
  border: 2px solid transparent;
  font-weight: 700;
}

.siteHeader__link[aria-current='page'] {
  border-color: var(--color-border);
  background: var(--color-accent);
}
</style>
