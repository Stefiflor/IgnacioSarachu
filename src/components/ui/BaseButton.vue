<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  variant: {
    type: String,
    default: 'primary', // primary, outline, text
    validator: (value: string) => ['primary', 'outline', 'text'].includes(value)
  },
  size: {
    type: String,
    default: 'md', // sm, md, lg
    validator: (value: string) => ['sm', 'md', 'lg'].includes(value)
  },
  href: {
    type: String,
    default: ''
  }
})

const classes = computed(() => {
  return [
    'base-button',
    `base-button--${props.variant}`,
    `base-button--${props.size}`
  ]
})
</script>

<template>
  <a v-if="href" :href="href" :class="classes">
    <slot></slot>
  </a>
  <button v-else :class="classes">
    <slot></slot>
  </button>
</template>

<style scoped>
.base-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  border-radius: var(--radius-md);
  transition: all var(--transition-normal);
  text-decoration: none;
}

/* Sizes */
.base-button--sm {
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
}

.base-button--md {
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
}

.base-button--lg {
  padding: 1rem 2rem;
  font-size: 1.125rem;
}

/* Variants */
.base-button--primary {
  background-color: var(--color-brand-primary);
  color: #FFFFFF;
  box-shadow: var(--shadow-sm);
}
.base-button--primary:hover {
  background-color: var(--color-brand-secondary);
  box-shadow: var(--shadow-md);
  transform: translateY(-2px);
}

.base-button--outline {
  background-color: transparent;
  color: var(--color-text-primary);
  border: 1px solid var(--color-text-muted);
}
.base-button--outline:hover {
  border-color: var(--color-text-primary);
  background-color: var(--color-bg-accent);
}

.base-button--text {
  background-color: transparent;
  color: var(--color-text-primary);
}
.base-button--text:hover {
  background-color: var(--color-bg-accent);
}
</style>
