<script setup lang="ts">
defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true },
  number: { type: Number, required: true }
})
</script>

<template>
  <div class="classic-card">
    <div class="card-number">{{ String(number).padStart(2, '0') }}</div>
    <h3 class="card-title">{{ title }}</h3>
    <p class="card-description">{{ description }}</p>
  </div>
</template>

<style scoped>
.classic-card {
  background-color: #FFFFFF;
  padding: 3rem 2rem;
  border-top: 3px solid transparent;
  box-shadow: var(--shadow-sm);
  transition: all var(--transition-normal);
  display: flex;
  flex-direction: column;
}

.classic-card:hover {
  border-top-color: var(--color-brand-accent);
  box-shadow: var(--shadow-md);
  transform: translateY(-3px);
}

.card-number {
  font-family: 'Playfair Display', serif;
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--color-bg-accent);
  line-height: 1;
  margin-bottom: 2rem;
  transition: color var(--transition-normal);
}

.classic-card:hover .card-number {
  color: var(--color-brand-accent);
}

.card-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--color-brand-primary);
  margin-bottom: 1rem;
}

.card-description {
  font-size: 1rem;
  color: var(--color-text-secondary);
  line-height: 1.7;
}
</style>
