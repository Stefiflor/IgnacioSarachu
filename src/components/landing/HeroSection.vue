<script setup lang="ts">
/* Hero Section Corporate */
</script>

<template>
  <section id="soluciones" class="hero bg-navy-gradient">
    <div class="container hero-container">
      
      <div class="hero-content">
        <h1 class="hero-title">
          Su tranquilidad financiera, <br/>
          <i class="hero-title-italic">garantizada.</i>
        </h1>
        
        <p class="hero-subtitle">
          Dele prioridad a la toma de decisiones en su negocio. Nosotros nos encargamos de brindarle certeza impositiva, contable y societaria con el máximo rigor profesional.
        </p>

        <div class="hero-actions">
          <a href="#contacto" class="btn-primary">Solicitar Entrevista</a>
          <a href="#servicios" class="btn-text">Conocer Estrategias &rarr;</a>
        </div>

        <div class="hero-credentials">
          <div class="cred-item">
            <span class="cred-number">Años</span>
            <span class="cred-label">de trayectoria sólida</span>
          </div>
          <div class="cred-divider"></div>
          <div class="cred-item">
            <span class="cred-number">Auditoría</span>
            <span class="cred-label">Prevención ante AFIP</span>
          </div>
        </div>
      </div>
      
      <!-- Retrato Profesional Clásico -->
      <div class="hero-portrait">
        <!-- Placeholder for a high end professional photo -->
        <div class="portrait-card">
          <div class="portrait-inner border-gold">
            <div class="portrait-name">Cr. Ignacio Sarachu</div>
            <div class="portrait-title">Mat. Tomo 4 Folio 95</div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: 5rem;
}

.hero-container {
  display: grid;
  grid-template-columns: 1fr;
  gap: 4rem;
  align-items: center;
}

@media (min-width: 1024px) {
  .hero-container {
    grid-template-columns: 1.1fr 0.9fr;
    gap: 5rem;
  }
}

.hero-content {
  max-width: 600px;
}

.hero-title {
  color: #FFFFFF;
  font-size: 2.75rem;
  margin-bottom: 1.5rem;
}

.hero-title-italic {
  color: var(--color-brand-accent);
  font-style: italic;
  font-weight: 600;
}

@media (min-width: 768px) {
  .hero-title {
    font-size: 3.5rem;
  }
}

.hero-subtitle {
  color: rgba(255, 255, 255, 0.85);
  font-size: 1.15rem;
  line-height: 1.8;
  margin-bottom: 3rem;
  font-weight: 300;
}

.hero-actions {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  margin-bottom: 4rem;
}

@media (min-width: 480px) {
  .hero-actions {
    flex-direction: row;
    align-items: center;
  }
}

.btn-primary {
  background-color: var(--color-brand-accent);
  color: var(--color-brand-primary);
  padding: 1rem 2.5rem;
  font-weight: 600;
  text-align: center;
  transition: all var(--transition-fast);
  font-family: 'Inter', sans-serif;
  letter-spacing: 0.02em;
}

.btn-primary:hover {
  background-color: var(--color-brand-accent-hover);
  transform: translateY(-2px);
}

.btn-text {
  color: #FFFFFF;
  font-weight: 500;
  font-family: 'Inter', sans-serif;
  transition: color var(--transition-fast);
}

.btn-text:hover {
  color: var(--color-brand-accent);
}

.hero-credentials {
  display: flex;
  align-items: center;
  gap: 2rem;
  border-top: 1px solid rgba(255,255,255,0.1);
  padding-top: 2rem;
}

.cred-item {
  display: flex;
  flex-direction: column;
}

.cred-number {
  color: var(--color-brand-accent);
  font-family: 'Playfair Display', serif;
  font-size: 1.25rem;
  font-weight: 600;
}

.cred-label {
  color: rgba(255,255,255,0.6);
  font-size: 0.85rem;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

.cred-divider {
  width: 1px;
  height: 40px;
  background-color: rgba(255,255,255,0.1);
}

.hero-portrait {
  position: relative;
  display: flex;
  justify-content: center;
}

.portrait-card {
  width: 100%;
  max-width: 400px;
  aspect-ratio: 3/4;
  background-color: rgba(255,255,255,0.05); /* Placeholder donde iría la foto */
  background-image: url('../../assets/images/hero-image.jpg'); /* Imagen de archivo propia */
  background-size: cover;
  background-position: center;
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
  position: relative;
}

.portrait-inner {
  position: absolute;
  bottom: -2rem; left: -2rem;
  background: white;
  padding: 1.5rem 2rem;
  box-shadow: var(--shadow-lg);
}

.border-gold {
  border-left: 3px solid var(--color-brand-accent);
}

.portrait-name {
  color: var(--color-brand-primary);
  font-family: 'Playfair Display', serif;
  font-weight: 700;
  font-size: 1.25rem;
  margin-bottom: 0.25rem;
}

.portrait-title {
  color: var(--color-text-secondary);
  font-size: 0.85rem;
  font-weight: 500;
}
</style>
