<script setup>
const flakes = Array.from({ length: 22 }, (_, index) => ({
  id: index,
  left: `${Math.random() * 100}%`,
  duration: `${11 + Math.random() * 13}s`,
  delay: `${Math.random() * -18}s`,
  size: `${1 + Math.random() * 2}px`,
  opacity: 0.16 + Math.random() * 0.24,
}))
</script>

<template>
  <div class="snowLayer" aria-hidden="true">
    <span
      v-for="flake in flakes"
      :key="flake.id"
      class="snowLayer__flake"
      :style="{
        left: flake.left,
        '--flake-duration': flake.duration,
        '--flake-delay': flake.delay,
        '--flake-size': flake.size,
        '--flake-opacity': flake.opacity,
      }"
    ></span>
  </div>
</template>

<style scoped lang="scss">
.snowLayer {
  position: fixed;
  inset: 0;
  z-index: -1;
  pointer-events: none;
  overflow: hidden;
}

.snowLayer__flake {
  position: absolute;
  top: -5%;
  width: var(--flake-size);
  height: var(--flake-size);
  border-radius: 50%;
  background: rgba(243, 245, 248, var(--flake-opacity));
  filter: blur(0.15px);
  animation: snowfall var(--flake-duration) linear infinite;
  animation-delay: var(--flake-delay);
}

@keyframes snowfall {
  0% {
    transform: translate3d(0, -4vh, 0);
  }

  100% {
    transform: translate3d(-2vw, 108vh, 0);
  }
}

@media (max-width: 900px) {
  .snowLayer {
    opacity: 0.45;
  }
}

@media (max-width: 700px), (prefers-reduced-motion: reduce) {
  .snowLayer {
    display: none;
  }
}
</style>
