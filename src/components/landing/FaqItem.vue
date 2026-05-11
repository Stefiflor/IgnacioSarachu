<script setup lang="ts">
import { ref } from 'vue'

defineProps({
  question: { type: String, required: true },
  answer: { type: String, required: true }
})

const isOpen = ref(false)

const toggle = () => {
  isOpen.value = !isOpen.value
}
</script>

<template>
  <div :class="['faq-item', { 'is-open': isOpen }]">
    <button class="faq-question" @click="toggle" :aria-expanded="isOpen">
      <span class="question-text">{{ question }}</span>
      <span class="faq-icon">
        <svg v-if="!isOpen" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
        </svg>
        <svg v-else viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M18 12H6" />
        </svg>
      </span>
    </button>
    <div class="faq-answer-wrapper" :style="{ maxHeight: isOpen ? '500px' : '0' }">
      <div class="faq-answer">
        <p>{{ answer }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.faq-item {
  border-bottom: 1px solid var(--color-bg-accent);
}

.faq-question {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5rem 0;
  color: var(--color-brand-primary);
  text-align: left;
  transition: color var(--transition-fast);
}

.faq-question:hover {
  color: var(--color-brand-accent);
}

.question-text {
  font-family: 'Playfair Display', serif;
  font-size: 1.25rem;
  font-weight: 600;
  padding-right: 2rem;
}

.faq-icon {
  flex-shrink: 0;
  width: 24px;
  height: 24px;
  color: var(--color-brand-accent);
}

.faq-answer-wrapper {
  overflow: hidden;
  transition: max-height var(--transition-normal);
}

.faq-answer {
  padding-bottom: 1.5rem;
  color: var(--color-text-secondary);
  font-size: 1.05rem;
  line-height: 1.7;
}
</style>
