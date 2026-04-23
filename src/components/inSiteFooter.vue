<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="siteFooter">
    <div class="siteFooter__brand">
      <img src="/assets/images/SomberDesignLogo.png" alt="SomberDesign logo" />
      <p>SomberDesign</p>
    </div>
    <p>© {{ currentYear }}</p>
  </footer>
</template>

<style scoped lang="scss">
.siteFooter {
  width: var(--site-width);
  margin: 1rem auto 0;
  padding: 0.8rem 0.6rem 2rem;
  display: flex;
  justify-content: space-between;
  gap: 1rem;
  font-size: 0.9rem;
  color: var(--color-text-muted);
}

.siteFooter__brand {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.siteFooter__brand p {
  color: var(--color-text-strong);
}

.siteFooter__brand img {
  width: 1.8rem;
  height: 1.8rem;
}

@media (max-width: 560px) {
  .siteFooter {
    flex-direction: column;
  }
}
</style>
