<script setup lang="ts">
import ProblemCard from './ProblemCard.vue'

const problems = [
  {
    title: "Incertidumbre Tributaria",
    description: "La normativa cambia constantemente. Desconocer qué impuestos aplican a su caso específico termina en severas penalidades económicas e intimaciones que podrían haberse evitado."
  },
  {
    title: "Presión de Organismos (AFIP/ARCA)",
    description: "El temor fundado ante notificaciones imprevistas, ejecuciones o auditorías, derivado de una deficiente o inexistente estrategia preventiva en su estructura contable."
  },
  {
    title: "Pérdida de Capital y Oportunidades",
    description: "Dejar caducar moratorias, exenciones fiscales o programas de sinceramiento que podrían mejorar radicalmente el flujo de caja de su empresa por falta de aviso oportuno."
  },
  {
    title: "Falta de Claridad Administrativa",
    description: "Imposibilidad de conocer la rentabilidad real de su negocio, desorden en la facturación y nula distinción entre el patrimonio personal y el societario."
  },
  {
    title: "Riesgos Laborales y Societarios",
    description: "Contingencias por relaciones laborales informales o encuadres societarios inadecuados que exponen su patrimonio a demandas legales paralizantes."
  },
  {
    title: "Distanciamiento Profesional",
    description: "Sentir que su consulta es ignorada. Trato impersonal, respuestas tardías y un estudio contable que solo liquida impuestos en lugar de asesorarlo verdaderamente."
  }
]
</script>

<template>
  <section id="problemas" class="problems-section section-padding">
    <div class="container">
      
      <div class="section-header">
        <span class="eyebrow">Diagnóstico Profesional</span>
        <h2 class="section-title">
          Los Desafíos que comprometen su <br/> 
          <i class="title-italic">estabilidad patrimonial.</i>
        </h2>
        <div class="header-divider"></div>
        <p class="section-subtitle">
          Sabemos que la rentabilidad de su negocio depende directamente de un marco fiscal robusto. La ausencia de este genera contingencias que no debería estar soportando.
        </p>
      </div>

      <div class="problems-grid">
        <ProblemCard 
          v-for="(item, index) in problems" 
          :key="index"
          :title="item.title"
          :description="item.description"
          :number="index + 1"
        />
      </div>

    </div>
  </section>
</template>

<style scoped>
.problems-section {
  background-color: var(--color-bg-secondary);
}

.section-header {
  text-align: center;
  max-width: 750px;
  margin: 0 auto 5rem;
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
  margin: 0 auto 2rem auto;
}

.section-subtitle {
  font-size: 1.15rem;
  color: var(--color-text-secondary);
}

.problems-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

@media (min-width: 768px) {
  .problems-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .problems-grid {
    grid-template-columns: repeat(3, 1fr);
    row-gap: 3rem;
  }
}
</style>
