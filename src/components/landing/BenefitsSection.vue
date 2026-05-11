<script setup lang="ts">
import BenefitCard from './BenefitCard.vue'

const benefits = [
  {
    title: "Atención Particular Nivel Directivo",
    description: "Cada cliente cuenta con línea directa y prioritaria al titular del estudio, sin intermediarios ni analistas junior de por medio en las decisiones críticas."
  },
  {
    title: "Compliance Fiscal del 100%",
    description: "Aseguramos el estricto cumplimiento normativo ante ARCA y AFIP. Evitamos multas, ejecuciones fiscales y sorpresas financieras que detengan su operatividad."
  },
  {
    title: "Protección Patrimonial y Confidencialidad",
    description: "Evaluamos sistemáticamente los encuadres jurídicos y societarios para optimizar y resguardar tanto el capital de su firma como su patrimonio personal bajo estricto secreto profesional."
  },
  {
    title: "Estrategia Activa, no Pasiva",
    description: "No esperamos a que venzan los impuestos para informarle. Proyectamos y analizamos su flujo de caja mensualmente para que pueda prever, reinvertir y escalar con certeza."
  }
]
</script>

<template>
  <section class="benefits-section section-padding">
    <div class="container">
      
      <div class="benefits-layout">
        <!-- Izquierda: Texto y Persuasión -->
        <div class="benefits-content">
          <span class="eyebrow">El Valor de la Excelencia</span>
          <h2 class="section-title">
            Más que un liquidador de impuestos, <br/>
            <i class="title-italic">un socio para su tranquilidad.</i>
          </h2>
          <div class="header-divider"></div>
          <p class="section-subtitle">
            Nuestro compromiso no es solo con los números, es con la continuidad a largo plazo de su patrimonio corporativo. Estas son las cuatro bases de nuestra firma.
          </p>

          <div class="cta-wrapper">
            <a href="#contacto" class="btn-outline">Reservar Consulta Privada</a>
          </div>
        </div>

        <!-- Derecha: Los beneficios en grilla -->
        <div class="benefits-grid">
          <BenefitCard 
            v-for="(item, index) in benefits"
            :key="index"
            :title="item.title"
            :description="item.description"
          />
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.benefits-section {
  background-color: var(--color-bg-secondary);
  border-top: 1px solid var(--color-bg-accent);
}

.benefits-layout {
  display: grid;
  grid-template-columns: 1fr;
  gap: 4rem;
}

@media (min-width: 1024px) {
  .benefits-layout {
    grid-template-columns: 0.9fr 1.1fr;
    align-items: center;
  }
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
    font-size: 2.5rem;
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
  margin: 0 0 2rem 0; /* Left aligned */
}

.section-subtitle {
  font-size: 1.125rem;
  color: var(--color-text-secondary);
  margin-bottom: 3rem;
  max-width: 90%;
}

.btn-outline {
  display: inline-block;
  border: 1px solid var(--color-brand-primary);
  color: var(--color-brand-primary);
  padding: 0.875rem 2rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 0.85rem;
  transition: all var(--transition-fast);
}

.btn-outline:hover {
  background-color: var(--color-brand-primary);
  color: white;
}

.benefits-grid {
  display: grid;
  grid-template-columns: 1fr;
}

@media (min-width: 640px) {
  .benefits-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
