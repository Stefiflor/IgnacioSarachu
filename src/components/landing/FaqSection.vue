<script setup lang="ts">
import FaqItem from './FaqItem.vue'

const faqs = [
  {
    question: "¿Gestionan clientes e intimaciones de extraña jurisdicción (fuera de TDF)?",
    answer: "Absolutamente. Dado nuestro enfoque tecnológico y los canales actuales de la Administración Federal de Ingresos Públicos, gestionamos y representamos a clientes corporativos en todo el territorio argentino con el mismo nivel de eficacia."
  },
  {
    question: "¿Asumen la defensa frente a fiscalizaciones y embargos?",
    answer: "Sí. Realizamos la representación formal ante ARCA, AREF e IGJ. Nuestro principal objetivo es destrabar operaciones comerciales bloqueadas y generar un entorno de defensa patrimonial sólido."
  },
  {
    question: "¿Cómo y cuándo se definen los honorarios del estudio?",
    answer: "En un marco de claridad absoluta. Tras la entrevista de diagnóstico inicial, presupuestamos un fee mensual transparente acorde al volumen y la complejidad operativa de su empresa, asegurando que no existan cobros sorpresivos."
  },
  {
    question: "¿El titular atiende personalmente mi caso?",
    answer: "Definitivamente. Es uno de nuestros pilares. Las resoluciones críticas y la estrategia fiscal de su negocio pasan exclusivamente por la revisión y directiva del Cr. Ignacio Sarachu, garantizando la altura profesional que requiere."
  }
]
</script>

<template>
  <section class="faq-section section-padding">
    <div class="container faq-container">
      
      <div class="faq-header">
        <span class="eyebrow">Aclaraciones Comunes</span>
        <h2 class="section-title">
          Preguntas <br/>
          <i class="title-italic">Frecuentes</i>
        </h2>
        <div class="header-divider"></div>
        <p class="section-subtitle">
          Entendemos que cambiar de estudio o iniciar uno nuevo genera interrogantes importantes. Aquí respondemos las dudas más habituales sobre nuestra metodología.
        </p>
      </div>

      <div class="faq-list">
        <FaqItem 
          v-for="(item, index) in faqs" 
          :key="index"
          :question="item.question"
          :answer="item.answer"
        />
      </div>

    </div>
  </section>
</template>

<style scoped>
.faq-section {
  background-color: var(--color-bg-primary);
}

.faq-container {
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
}

@media (min-width: 992px) {
  .faq-container {
    grid-template-columns: 1fr 1.5fr;
    gap: 6rem;
  }
}

.faq-header {
  max-width: 400px;
}

.eyebrow {
  display: block;
  font-family: 'Inter', sans-serif;
  color: var(--color-brand-accent);
  text-transform: uppercase;
  font-weight: 600;
  letter-spacing: 0.1em;
  font-size: 0.85rem;
  margin-bottom: 1rem;
}

.section-title {
  font-size: 2.25rem;
  margin-bottom: 1.5rem;
  color: var(--color-brand-primary);
  line-height: 1.2;
}

@media (min-width: 768px) {
  .section-title {
    font-size: 2.75rem;
  }
}

.title-italic {
  font-family: 'Playfair Display', serif;
  font-style: italic;
  font-weight: 600;
  color: var(--color-text-primary);
}

.header-divider {
  width: 60px;
  height: 2px;
  background-color: var(--color-brand-accent);
  margin-bottom: 2rem;
}

.section-subtitle {
  font-size: 1.15rem;
  color: var(--color-text-secondary);
}

.faq-list {
  display: flex;
  flex-direction: column;
}
</style>
