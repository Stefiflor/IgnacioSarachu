<script setup lang="ts">
import ServiceCard from './ServiceCard.vue'

// SVG Icons en crudo para ser inyectados en la card y evitar dependencias complejas. Estilo line.
const iconImpositivo = `<svg fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M9 14l6-6m-5.5.5h.01m4.99 5h.01M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16l3.5-2 3.5 2 3.5-2 3.5 2z"></path></svg>`
const iconLaboral = `<svg fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"></path></svg>`
const iconContable = `<svg fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"></path></svg>`
const iconSocietario = `<svg fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"></path></svg>`

const services = [
  {
    title: "Gestión Impositiva y Fiscal",
    description: "Liquidación y planificación fiscal estratégica. Minimizamos sus cargas tributarias respetando rigurosamente el marco legal, garantizando que su empresa pague lo justo.",
    icon: iconImpositivo,
    features: [
      "Liquidación Mensual/Anual de Impuestos",
      "Planificación Estratégica Fiscal",
      "Atención Integral de Inspecciones",
      "Blanqueos y Moratorias (ARCA)"
    ]
  },
  {
    title: "Asesoramiento Laboral Integral",
    description: "Confección y liquidación de haberes, cargas sociales y gestión de nóminas, protegiendo su patrimonio frente a contingencias y juicios laborales.",
    icon: iconLaboral,
    features: [
      "Liquidación de Sueldos y Cargas",
      "Altas, Bajas y Modificaciones (AFIP)",
      "Análisis de Contratos Laborales",
      "Auditoría Preventiva Laboral"
    ]
  },
  {
    title: "Auditoría Financiera y Contable",
    description: "Visibilidad total del estado de sus finanzas. Entregamos reportes precisos, flujos de caja proyectados y estados contables dictaminados para terceros.",
    icon: iconContable,
    features: [
      "Confección de Balances y Estados",
      "Certificaciones de Ingresos",
      "Dashboard y Reportes C-Level",
      "Auditoría Interna y Operativa"
    ]
  },
  {
    title: "Estructuración Societaria",
    description: "Constitución de la figura legal más idónea para la protección de sus bienes, minimizando riesgos ante potenciales litigios comerciales o laborales.",
    icon: iconSocietario,
    features: [
      "Constitución de Sociedades (SRL, SA, SAS)",
      "Mantenimiento de Libros y Actas",
      "Reorganizaciones y Fusiones",
      "Asesoramiento a Directorios y Socios"
    ]
  }
]
</script>

<template>
  <section id="servicios" class="services-section section-padding">
    <div class="container">

      <div class="section-header">
        <span class="eyebrow">Áreas de Especialidad</span>
        <h2 class="section-title">
          Servicios integrales para la <br/>
          <i class="title-italic">gestión avanzada de su empresa.</i>
        </h2>
        <div class="header-divider"></div>
        <p class="section-subtitle">
          Proveemos un ecosistema de servicios interconectados liderados por un profesional matriculado, diseñados para resguardar su capital mientras su firma escala.
        </p>
      </div>

      <div class="services-grid">
        <ServiceCard 
          v-for="(service, index) in services" 
          :key="index"
          :title="service.title"
          :description="service.description"
          :icon="service.icon"
          :features="service.features"
        />
      </div>

    </div>
  </section>
</template>

<style scoped>
.services-section {
  background-color: var(--color-bg-primary); /* Blanco o tono claro base */
}

.section-header {
  text-align: center;
  max-width: 800px;
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

.services-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

@media (min-width: 768px) {
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
