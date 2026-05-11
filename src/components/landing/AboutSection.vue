<script setup lang="ts">
// AboutSection Corporate Style
</script>

<template>
  <section id="sobre-mi" class="about-section section-padding">
    <div class="container">
      <div class="about-grid">
        
        <div class="about-visual">
          <div class="photo-frame">
            <!-- Imagen real posterior de Ignacio ira aca -->
            <div class="photo-placeholder"></div>
            <div class="seal-badge">
              <span class="seal-text">UNTDF</span>
              <span class="seal-sub">Alumni</span>
            </div>
          </div>
        </div>

        <div class="about-content">
          <span class="eyebrow">Dirección General</span>
          <h2 class="section-title">Cr. Ignacio Sarachu</h2>
          
          <div class="credentials">
            <span class="cred-item">Contador Público Nacional</span>
            <span class="cred-dot">&bull;</span>
            <span class="cred-item">Universidad Nacional de Tierra del Fuego</span>
          </div>
          
          <p class="about-text">
            Mi misión es brindar <strong>certeza financiera y patrimonial</strong> a empresarios, profesionales y mesas directivas que buscan trascender. Entiendo que la contabilidad no se trata de completar formularios para el Estado, sino de construir una estructura robusta donde su capital pueda crecer de manera predecible y segura.
          </p>
          
          <p class="about-text">
            Le ofrezco la tranquilidad de saber que sus obligaciones fiscales están meticulosamente revisadas y optimizadas, para que pueda poner el 100% de su capacidad intelectual en lo que mejor hace: liderar su negocio.
          </p>

          <div class="matricula-box">
            <p class="matricula-title">Matrícula Habilitante</p>
            <p class="matricula-numbers">Tomo 4 — Folio 95</p>
            <p class="matricula-gov">Consejo Profesional de Ciencias Económicas</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  background-color: var(--color-bg-primary);
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 4rem;
}

@media (min-width: 992px) {
  .about-grid {
    grid-template-columns: 0.8fr 1.2fr;
    align-items: center;
    gap: 6rem;
  }
}

.about-visual {
  position: relative;
  display: flex;
  justify-content: center;
}

.photo-frame {
  position: relative;
  width: 100%;
  max-width: 450px;
  aspect-ratio: 4/5;
  background-color: var(--color-bg-accent);
  box-shadow: var(--shadow-sm);
  border-radius: var(--radius-sm);
}

.photo-placeholder {
  width: 100%;
  height: 100%;
  background-image: url('../../assets/images/about-image.jpg');
  background-size: cover;
  background-position: center;
  border-radius: inherit;
}

.seal-badge {
  position: absolute;
  bottom: -1.5rem;
  right: -1.5rem;
  width: 100px;
  height: 100px;
  background-color: var(--color-brand-primary);
  color: var(--color-brand-accent);
  border-radius: 50%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-shadow: var(--shadow-md);
  border: 4px solid var(--color-bg-primary);
}

.seal-text {
  font-family: 'Playfair Display', serif;
  font-weight: 700;
  font-size: 1.2rem;
  letter-spacing: 1px;
}

.seal-sub {
  font-size: 0.6rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

.about-content {
  padding-left: 0;
}

@media (min-width: 992px) {
  .about-content {
    padding-left: 2rem;
  }
}

.eyebrow {
  display: block;
  color: var(--color-brand-accent);
  text-transform: uppercase;
  font-weight: 600;
  letter-spacing: 0.1em;
  font-size: 0.85rem;
  margin-bottom: 0.5rem;
}

.section-title {
  font-size: 2.5rem;
  color: var(--color-brand-primary);
  margin-bottom: 1rem;
}

.credentials {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 2rem;
  font-size: 0.95rem;
  color: var(--color-text-secondary);
  font-weight: 500;
}

.cred-dot {
  color: var(--color-brand-accent);
}

.about-text {
  font-size: 1.1rem;
  color: var(--color-text-secondary);
  margin-bottom: 1.5rem;
  line-height: 1.8;
}

.about-text strong {
  color: var(--color-brand-primary);
  font-weight: 600;
}

.matricula-box {
  margin-top: 3rem;
  padding: 1.5rem 2rem;
  background-color: var(--color-bg-secondary);
  border-left: 3px solid var(--color-brand-accent);
  display: inline-block;
}

.matricula-title {
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--color-text-muted);
  margin-bottom: 0.25rem;
}

.matricula-numbers {
  font-family: 'Playfair Display', serif;
  font-size: 1.35rem;
  font-weight: 600;
  color: var(--color-brand-primary);
  margin-bottom: 0.15rem;
}

.matricula-gov {
  font-size: 0.85rem;
  color: var(--color-text-secondary);
}
</style>
