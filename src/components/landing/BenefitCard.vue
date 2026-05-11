<script setup lang="ts">
defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true }
})
</script>

<template>
  <div class="benefit-card">
    <div class="benefit-marker"></div>
    <h3 class="benefit-title">{{ title }}</h3>
    <p class="benefit-description">{{ description }}</p>
  </div>
</template>

<style scoped>
.benefit-card {
  padding: 2.5rem;
  background-color: var(--color-bg-primary);
  border-left: 1px solid var(--color-bg-accent);
  transition: all var(--transition-normal);
  position: relative;
}

.benefit-card:hover {
  background-color: white;
  box-shadow: var(--shadow-sm);
  border-left-color: transparent;
}

.benefit-marker {
  position: absolute;
  top: 0; left: -1px;
  width: 3px; height: 0;
  background-color: var(--color-brand-accent);
  transition: height var(--transition-normal);
}

.benefit-card:hover .benefit-marker {
  height: 100%;
}

.benefit-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.35rem;
  color: var(--color-brand-primary);
  margin-bottom: 1rem;
}

.benefit-description {
  color: var(--color-text-secondary);
  font-size: 1rem;
  line-height: 1.6;
}
</style>
