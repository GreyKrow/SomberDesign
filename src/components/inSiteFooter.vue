<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="siteFooter">
    <p>SomberDesign — Minimal web design studio.</p>
    <p>© {{ currentYear }}</p>
  </footer>
</template>

<style scoped lang="scss">
.siteFooter {
  width: var(--site-width);
  margin: 0 auto;
  padding: 1.25rem 0 2rem;
  display: flex;
  justify-content: space-between;
  gap: 1rem;
  font-size: 0.9rem;
}
</style>
