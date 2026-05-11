<script setup lang="ts">
// Footer corporativo
</script>

<template>
  <footer class="footer">
    <div class="container footer-container">
      
      <div class="footer-top">
        <div class="footer-brand">
          <div class="logo">
            <span class="logo-name">Ignacio Sarachu</span>
            <span class="logo-title">Estudio Contable</span>
          </div>
          <p class="brand-desc">
            Asesoramiento integral y estructuración patrimonial para el cumplimiento normativo con excelencia y previsión.
          </p>
        </div>

        <div class="footer-links">
          <h4 class="links-title">Navegación</h4>
          <ul>
            <li><a href="#soluciones">Inicio</a></li>
            <li><a href="#problemas">Desafíos</a></li>
            <li><a href="#servicios">Especialidades</a></li>
            <li><a href="#sobre-mi">Dirección</a></li>
          </ul>
        </div>

        <div class="footer-contact">
          <h4 class="links-title">Contacto</h4>
          <p class="contact-item">CPCE. Tierra del Fuego</p>
          <p class="contact-item">Tomo 4, Folio 95</p>
          <a href="#contacto" class="btn-footer">Solicitar Entrevista</a>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; {{ new Date().getFullYear() }} Ignacio Sarachu. Estudio Contable. Reservados todos los derechos.</p>
        <div class="legal-links">
          <a href="#">Términos y Condiciones</a>
          <a href="#">Confidencialidad</a>
        </div>
      </div>

    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: var(--color-brand-primary);
  color: rgba(255, 255, 255, 0.7);
  padding: 5rem 0 2rem 0;
}

.footer-top {
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
  margin-bottom: 4rem;
}

@media (min-width: 768px) {
  .footer-top {
    grid-template-columns: 2fr 1fr 1fr;
    gap: 4rem;
  }
}

.logo-name {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  line-height: 1;
  display: block;
}

.logo-title {
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--color-brand-accent);
  display: block;
  margin-bottom: 1.5rem;
}

.brand-desc {
  max-width: 350px;
  font-size: 0.95rem;
  line-height: 1.6;
}

.links-title {
  color: white;
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 1.5rem;
}

.footer-links ul {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.footer-links a {
  font-size: 0.95rem;
  transition: color var(--transition-fast);
}

.footer-links a:hover {
  color: var(--color-brand-accent);
}

.contact-item {
  font-size: 0.95rem;
  margin-bottom: 0.5rem;
}

.btn-footer {
  display: inline-block;
  margin-top: 1.5rem;
  border-bottom: 1px solid var(--color-brand-accent);
  color: var(--color-brand-accent);
  font-weight: 600;
  font-size: 0.9rem;
  padding-bottom: 0.25rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.btn-footer:hover {
  color: white;
  border-bottom-color: white;
}

.footer-bottom {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 2rem;
  font-size: 0.85rem;
}

@media (min-width: 768px) {
  .footer-bottom {
    flex-direction: row;
    justify-content: space-between;
  }
}

.legal-links {
  display: flex;
  gap: 2rem;
}

.legal-links a:hover {
  color: white;
}
</style>
