<script setup lang="ts">
defineProps({
  icon: { type: String, required: true },
  title: { type: String, required: true },
  description: { type: String, required: true },
  features: { type: Array as () => string[], required: true }
})
</script>

<template>
  <div class="service-card">
    <div class="card-header">
      <div class="icon-wrapper" v-html="icon"></div>
      <h3 class="service-title">{{ title }}</h3>
    </div>
    
    <p class="service-description">{{ description }}</p>

    <div class="divider"></div>

    <ul class="features-list">
      <li v-for="(feat, idx) in features" :key="idx" class="feature-item">
        <svg class="check-icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
        </svg>
        <span>{{ feat }}</span>
      </li>
    </ul>

    <div class="card-footer">
      <a href="#contacto" class="btn-link">Consultar Especialidad &rarr;</a>
    </div>
  </div>
</template>

<style scoped>
.service-card {
  background-color: var(--color-bg-primary);
  border: 1px solid var(--color-bg-accent);
  border-radius: var(--radius-md);
  padding: 3rem 2.5rem;
  box-shadow: var(--shadow-sm);
  transition: all var(--transition-normal);
  display: flex;
  flex-direction: column;
  height: 100%;
}

.service-card:hover {
  box-shadow: var(--shadow-lg);
  border-color: var(--color-brand-primary);
  transform: translateY(-5px);
}

.card-header {
  margin-bottom: 1.5rem;
}

.icon-wrapper {
  color: var(--color-brand-accent);
  margin-bottom: 1.5rem;
  width: 48px;
  height: 48px;
}

/* Forzar que los SVGs inyectados tomen el tamaño */
.icon-wrapper :deep(svg) {
  width: 100%;
  height: 100%;
}

.service-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  color: var(--color-brand-primary);
  line-height: 1.2;
}

.service-description {
  color: var(--color-text-secondary);
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 2rem;
}

.divider {
  width: 100%;
  height: 1px;
  background-color: var(--color-bg-accent);
  margin-bottom: 2rem;
}

.features-list {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 2rem;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  font-size: 0.95rem;
  color: var(--color-text-primary);
  font-weight: 500;
}

.check-icon {
  width: 18px;
  height: 18px;
  color: var(--color-brand-accent);
  margin-top: 0.15rem;
  flex-shrink: 0;
}

.card-footer {
  margin-top: auto;
}

.btn-link {
  color: var(--color-brand-primary);
  font-weight: 600;
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  transition: color var(--transition-fast);
}

.btn-link:hover {
  color: var(--color-brand-accent);
}
</style>
