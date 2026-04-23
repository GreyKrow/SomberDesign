<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="siteFooter">
    <div class="siteFooter__brand">
      <img src="/assets/images/SomberDesignLogo.png" alt="SomberDesign logo" />
      <p>SomberDesign — Minimal web design studio.</p>
    </div>
    <p>© {{ currentYear }}</p>
  </footer>
</template>

<style scoped lang="scss">
.siteFooter {
  width: var(--site-width);
  margin: 1rem auto 0;
  padding: 1rem 1.2rem 2rem;
  display: flex;
  justify-content: space-between;
  gap: 1rem;
  font-size: 0.9rem;
  color: var(--color-text-muted);
}

.siteFooter__brand {
  display: flex;
  align-items: center;
  gap: 0.6rem;
}

.siteFooter__brand img {
  width: 1.8rem;
  height: 1.8rem;
}
</style>
