<script setup>
import content from '@/config/content.json';
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark position-fixed">
    <div class="container-fluid">
      <RouterLink class="navbar-brand" to="/">
        <img :src="content.brand.logo" alt="" width="60" height="60">
        {{ content.brand.username }}
      </RouterLink>
      <button class="navbar-toggler" data-bs-toggle="collapse" data-bs-target="#navbarCollapse">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarCollapse">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <slot name="left"></slot>
        </ul>
        <ul class="navbar-nav mb-2 mb-lg-0">
          <slot name="right"></slot>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style lang="scss">
.navbar {
  z-index: 1000;
  width: 100%;
  top: 0;
}

@media (max-width: 992px) {
  .nav-item {
    width: 100%;
    text-align: center;
  }
}

.nav-link {
  cursor: pointer;
  -webkit-transition: color 0.5s ease-in, color 0.1s ease-out !important;
  transition: color 0.5s ease-in, color 0.1s ease-out !important;
  color: var(--text-color) !important;

  &:hover {
    color: var(--hover-color) !important;
  }
}
</style>

<style lang="scss" scoped>
.navbar {
  padding-top: 0 !important;
  padding-bottom: 0 !important;
}

.navbar-brand {
  color: var(--text-color);
}

.navbar-dark .navbar-toggler {
    color: rgba(255, 255, 255, 0.55);
    border: none !important;
}
</style>
