<script setup lang="ts">
import AppNavbar from '../components/landing/AppNavbar.vue'
import AppFooter from '../components/landing/AppFooter.vue'
</script>

<template>
  <div class="layout-wrapper">
    <AppNavbar />
    
    <main class="main-content">
      <slot></slot>
    </main>

    <AppFooter />
  </div>
</template>

<style scoped>
.layout-wrapper {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.main-content {
  flex: 1;
}
</style>
