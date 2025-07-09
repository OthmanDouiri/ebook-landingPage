<script setup>
import { ref } from 'vue'

const scrollToPricing = () => {
  document.getElementById('pricing').scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-white fixed-top">
    <div class="container">
      <!-- Logo -->
      <a class="navbar-brand fw-bold" href="#hero">
        <div class="logo-container">
          <div class="logo-icon">
            <i class="fas fa-book-open"></i>
          </div>
          <span class="logo-text">eBook Pro</span>
        </div>
      </a>

      <!-- Toggle button para móvil -->
      <button 
        class="navbar-toggler border-0" 
        type="button" 
        data-bs-toggle="collapse" 
        data-bs-target="#navbarNav"
        aria-controls="navbarNav" 
        aria-expanded="false" 
        aria-label="Toggle navigation"
      >
        <i class="fas fa-bars text-muted"></i>
      </button>

      <!-- Menu items -->
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto align-items-center">
          <li class="nav-item">
            <a class="nav-link" href="#features">Características</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#author">Autor</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#testimonials">Testimonios</a>
          </li>
          <li class="nav-item ms-lg-3">
            <button 
              @click="scrollToPricing"
              class="btn btn-custom-primary"
            >
              <i class="fas fa-shopping-cart me-2"></i>
              Comprar Ahora
            </button>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  transition: all 0.2s ease;
  box-shadow: var(--shadow-sm);
  backdrop-filter: blur(10px);
  background-color: rgba(255, 255, 255, 0.95) !important;
  border-bottom: 1px solid var(--border-light);
}

.logo-container {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.logo-icon {
  width: 2.5rem;
  height: 2.5rem;
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  border-radius: var(--radius-lg);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.125rem;
}

.logo-text {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
}

.navbar-brand {
  text-decoration: none;
}

.navbar-brand:hover .logo-text {
  color: var(--primary-color);
}

.nav-link {
  font-weight: 500;
  color: var(--text-secondary) !important;
  margin: 0 0.5rem;
  padding: 0.5rem 1rem !important;
  border-radius: var(--radius-md);
  transition: all 0.2s ease;
  font-size: 0.875rem;
}

.nav-link:hover {
  color: var(--primary-color) !important;
  background-color: rgba(59, 130, 246, 0.05);
}

.navbar-toggler:focus {
  box-shadow: none;
}

/* Asegurar que el contenido no quede oculto detrás del navbar fijo */
body {
  padding-top: 80px;
}

@media (max-width: 991px) {
  body {
    padding-top: 70px;
  }
  
  .navbar-nav {
    text-align: center;
    padding-top: 1rem;
    gap: 0.5rem;
  }
  
  .nav-item {
    margin: 0.25rem 0;
  }
  
  .nav-link {
    margin: 0;
    width: 100%;
  }
}

@media (max-width: 575px) {
  .logo-icon {
    width: 2rem;
    height: 2rem;
    font-size: 1rem;
  }
  
  .logo-text {
    font-size: 1.125rem;
  }
}
</style>
