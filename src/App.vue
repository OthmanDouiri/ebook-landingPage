<script setup>
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
import Features from './components/Features.vue'
import AboutAuthor from './components/AboutAuthor.vue'
import EmailCapture from './components/EmailCapture.vue'
import Testimonials from './components/Testimonials.vue'
import Pricing from './components/Pricing.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div id="app">
    <!-- Header con navegación -->
    <Header />
    
    <!-- Sección Hero -->
    <HeroSection />
    
    <!-- Características del eBook -->
    <Features />
    
    <!-- Sobre el autor -->
    <AboutAuthor />
    
    <!-- Captura de email -->
    <EmailCapture />
    
    <!-- Testimonios -->
    <Testimonials />
    
    <!-- Precios -->
    <Pricing />
    
    <!-- Footer -->
    <Footer />
  </div>
</template>

<style>
/* Variables personalizadas - Paleta minimalista: Negro, Rojo, Blanco */
:root {
  --primary-color: #dc2626;       /* Rojo principal */
  --secondary-color: #991b1b;     /* Rojo oscuro */
  --accent-color: #dc2626;        /* Rojo acento */
  --error-color: #dc2626;         /* Rojo error */
  --text-primary: #000000;        /* Negro para texto principal */
  --text-secondary: #404040;      /* Gris oscuro para texto secundario */
  --text-muted: #666666;          /* Gris medio para texto deshabilitado */
  --bg-primary: #ffffff;          /* Blanco principal */
  --bg-secondary: #ffffff;        /* Blanco secundario */
  --bg-dark: #000000;             /* Negro para fondos oscuros */
  --border-light: #e0e0e0;        /* Bordes suaves grises */
  --border-medium: #cccccc;       /* Bordes medios grises */
  --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
  --radius-sm: 0.375rem;          /* 6px */
  --radius-md: 0.5rem;            /* 8px */
  --radius-lg: 0.75rem;           /* 12px */
  --radius-xl: 1rem;              /* 16px */
}

/* Estilos globales */
body {
  margin: 0;
  padding: 0;
  font-size: 16px;
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: var(--text-primary);
  background-color: var(--bg-primary);
}

/* Smooth scrolling */
html {
  scroll-behavior: smooth;
}

/* Botones personalizados - Estilo moderno */
.btn-custom-primary {
  background-color: var(--primary-color);
  border-color: var(--primary-color);
  color: white;
  font-weight: 500;
  padding: 0.75rem 1.5rem;
  border-radius: var(--radius-lg);
  transition: all 0.2s ease;
  font-size: 0.875rem;
  box-shadow: var(--shadow-sm);
}

.btn-custom-primary:hover {
  background-color: var(--secondary-color);
  border-color: var(--secondary-color);
  color: white;
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}

.btn-custom-secondary {
  background-color: var(--secondary-color);
  border-color: var(--secondary-color);
  color: white;
  font-weight: 500;
  padding: 0.75rem 1.5rem;
  border-radius: var(--radius-lg);
  transition: all 0.2s ease;
  font-size: 0.875rem;
  box-shadow: var(--shadow-sm);
}

.btn-custom-secondary:hover {
  background-color: var(--primary-color);
  border-color: var(--primary-color);
  color: white;
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}

.btn-outline-custom {
  background-color: transparent;
  border: 1px solid var(--border-medium);
  color: var(--text-primary);
  font-weight: 500;
  padding: 0.75rem 1.5rem;
  border-radius: var(--radius-lg);
  transition: all 0.2s ease;
  font-size: 0.875rem;
}

.btn-outline-custom:hover {
  background-color: var(--bg-secondary);
  border-color: var(--primary-color);
  color: var(--primary-color);
  box-shadow: var(--shadow-sm);
}

/* Secciones */
.section-padding {
  padding: 5rem 0;
}

.section-light {
  background-color: var(--bg-secondary);
}

.section-muted {
  background-color: var(--bg-primary);
}

/* Cards modernas */
.card-modern {
  background: var(--bg-secondary);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-sm);
  transition: all 0.2s ease;
}

.card-modern:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-2px);
}

/* Sombras personalizadas */
.custom-shadow {
  box-shadow: var(--shadow-md);
}

.custom-shadow-hover {
  transition: all 0.2s ease;
}

.custom-shadow-hover:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-2px);
}

/* Badges modernos */
.badge-modern {
  background-color: var(--primary-color);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: var(--radius-xl);
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.025em;
}

.badge-success {
  background-color: var(--accent-color);
}

.badge-warning {
  background-color: #f59e0b;
}

/* Animaciones suaves */
.fade-in {
  animation: fadeIn 0.6s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Tipografía mejorada */
.text-gradient {
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Responsive */
@media (max-width: 768px) {
  .section-padding {
    padding: 3rem 0;
  }
  
  .btn-custom-primary,
  .btn-custom-secondary,
  .btn-outline-custom {
    padding: 0.625rem 1.25rem;
    font-size: 0.875rem;
  }
}
</style>
