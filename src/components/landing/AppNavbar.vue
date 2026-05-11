<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

const toggleMobile = () => {
  isMobileOpen.value = !isMobileOpen.value
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header :class="['navbar-classic', { 'scrolled': isScrolled || isMobileOpen }]">
    <div class="container navbar-container">
      
      <!-- Lema o Nombre -->
      <div class="logo">
        <span class="logo-name">Ignacio Sarachu</span>
        <span class="logo-title">Estudio Contable</span>
      </div>

      <!-- Navegación Desktop -->
      <nav class="nav-links">
        <a href="#soluciones" class="nav-link">Inicio</a>
        <a href="#problemas" class="nav-link">Desafíos</a>
        <a href="#servicios" class="nav-link">Servicios</a>
      </nav>

      <!-- Botón Elegante Desktop -->
      <div class="nav-cta">
        <a href="#contacto" class="btn-classic">Contacto Directo</a>
      </div>

      <!-- Mobile Toggle Button -->
      <button class="mobile-toggle" @click="toggleMobile" aria-label="Toggle menu">
        <svg v-if="!isMobileOpen" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg v-else fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>

    </div>

    <!-- Mobile Menu Slide -->
    <div :class="['mobile-menu', { 'mobile-menu--open': isMobileOpen }]">
      <div class="mobile-nav-links">
        <a href="#soluciones" class="mobile-link" @click="toggleMobile">Inicio</a>
        <a href="#problemas" class="mobile-link" @click="toggleMobile">Desafíos</a>
        <a href="#servicios" class="mobile-link" @click="toggleMobile">Servicios</a>
        <a href="#sobre-mi" class="mobile-link" @click="toggleMobile">Dirección</a>
        <a href="#contacto" class="mobile-btn" @click="toggleMobile">Contacto Directo</a>
      </div>
    </div>
  </header>
</template>

<style scoped>
.navbar-classic {
  position: fixed;
  top: 0; left: 0; width: 100%;
  z-index: 100;
  background-color: transparent;
  padding: 1.5rem 0;
  transition: all var(--transition-normal);
  border-bottom: 1px solid transparent;
}

@media (min-width: 768px) {
  .navbar-classic {
    padding: 2rem 0;
  }
}

.navbar-classic.scrolled {
  background-color: rgba(255, 255, 255, 0.98);
  padding: 1rem 0;
  border-bottom: 1px solid var(--color-bg-accent);
  box-shadow: 0 2px 10px rgba(0,0,0,0.03);
}

.navbar-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
  z-index: 101;
}

.logo {
  display: flex;
  flex-direction: column;
  gap: 0.1rem;
}

.logo-name {
  font-family: 'Playfair Display', serif;
  font-size: 1.3rem;
  font-weight: 700;
  color: #FFFFFF;
  line-height: 1;
  transition: color var(--transition-normal);
}

@media (min-width: 768px) {
  .logo-name {
    font-size: 1.5rem;
  }
}

.navbar-classic.scrolled .logo-name {
  font-size: 1.25rem;
  color: var(--color-brand-primary);
}

.logo-title {
  font-size: 0.7rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--color-brand-accent);
}

.nav-links, .nav-cta {
  display: none;
}

@media (min-width: 768px) {
  .nav-links {
    display: flex;
    gap: 2rem;
  }
  .nav-cta {
    display: block;
  }
}

@media (min-width: 1024px) {
  .nav-links { gap: 3rem; }
}

.nav-link {
  font-size: 0.95rem;
  font-weight: 500;
  color: rgba(255, 255, 255, 0.85);
  position: relative;
  transition: color var(--transition-fast);
}

.navbar-classic.scrolled .nav-link {
  color: var(--color-text-primary);
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0; height: 1px;
  bottom: -4px; left: 0;
  background-color: var(--color-brand-accent);
  transition: width var(--transition-fast);
}

.nav-link:hover {
  color: #FFFFFF;
}

.navbar-classic.scrolled .nav-link:hover {
  color: var(--color-brand-primary);
}

.nav-link:hover::after {
  width: 100%;
}

.btn-classic {
  border: 1px solid rgba(255, 255, 255, 0.5);
  color: #FFFFFF;
  padding: 0.6rem 1.5rem;
  font-weight: 500;
  font-size: 0.9rem;
  background: transparent;
  transition: all var(--transition-fast);
  white-space: nowrap;
}

.navbar-classic.scrolled .btn-classic {
  padding: 0.5rem 1.25rem;
  border-color: var(--color-brand-primary);
  color: var(--color-brand-primary);
}

.btn-classic:hover {
  background-color: #FFFFFF;
  color: var(--color-brand-primary);
}

.navbar-classic.scrolled .btn-classic:hover {
  background-color: var(--color-brand-primary);
  color: #FFFFFF;
}

/* Mobile Toggle */
.mobile-toggle {
  display: block;
  width: 32px; height: 32px;
  color: #FFFFFF;
  transition: color var(--transition-fast);
}

.navbar-classic.scrolled .mobile-toggle {
  color: var(--color-brand-primary);
}

@media (min-width: 768px) {
  .mobile-toggle {
    display: none;
  }
}

/* Mobile Menu */
.mobile-menu {
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  background-color: #FFFFFF;
  padding: 0 1.5rem;
  max-height: 0;
  overflow: hidden;
  transition: max-height var(--transition-normal);
  border-bottom: 1px solid var(--color-bg-accent);
  box-shadow: 0 10px 15px rgba(0,0,0,0.05);
}

.mobile-menu--open {
  max-height: 400px;
  padding-bottom: 1.5rem;
}

.mobile-nav-links {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding-top: 1.5rem;
}

.mobile-link {
  font-size: 1.1rem;
  font-family: 'Playfair Display', serif;
  font-weight: 600;
  color: var(--color-brand-primary);
  border-bottom: 1px solid var(--color-bg-accent);
  padding-bottom: 0.5rem;
}

.mobile-btn {
  display: inline-block;
  margin-top: 0.5rem;
  background-color: var(--color-brand-primary);
  color: white;
  text-align: center;
  padding: 0.75rem 1rem;
  font-weight: 600;
  border-radius: var(--radius-sm);
}
</style>
