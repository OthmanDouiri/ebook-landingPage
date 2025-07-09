<script setup>
const scrollToPricing = () => {
  document.getElementById('pricing').scrollIntoView({ behavior: 'smooth' })
}

const scrollToEmail = () => {
  document.getElementById('email-capture').scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
  <section id="hero" class="hero-section">
    <div class="container">
      <div class="row align-items-center min-vh-100 py-5">
        <!-- Contenido Principal -->
        <div class="col-lg-6 order-lg-1 order-2">
          <div class="hero-content fade-in">
            <div class="badge-modern bg-danger text-white mb-4">
              <i class="fas fa-star me-2"></i>
              Bestseller Digital
            </div>
            
            <h1 class="hero-title mb-4">
              Domina el <span class="text-danger">Marketing Digital</span> 
              en 30 Días
            </h1>
            
            <p class="hero-subtitle mb-5">
              Descubre los secretos que usan los expertos para generar 
              <span class="highlight text-danger fw-bold">+$10,000</span> mensuales con marketing digital. 
              Una guía práctica y paso a paso con estrategias reales.
            </p>

            <!-- Beneficios rápidos -->
            <div class="benefits-list mb-5">
              <div class="benefit-item">
                <div class="benefit-icon">
                  <i class="fas fa-check"></i>
                </div>
                <span>200+ páginas de contenido práctico</span>
              </div>
              <div class="benefit-item">
                <div class="benefit-icon">
                  <i class="fas fa-check"></i>
                </div>
                <span>15 plantillas y herramientas incluidas</span>
              </div>
              <div class="benefit-item">
                <div class="benefit-icon">
                  <i class="fas fa-check"></i>
                </div>
                <span>Acceso de por vida + actualizaciones gratuitas</span>
              </div>
            </div>

            <!-- Botones de acción -->
            <div class="hero-buttons mb-4">
              <button 
                @click="scrollToPricing"
                class="btn btn-custom-primary btn-lg me-3 mb-3"
              >
                <i class="fas fa-shopping-cart me-2"></i>
                Comprar por $47
              </button>
              
              <button 
                @click="scrollToEmail"
                class="btn btn-outline-custom btn-lg mb-3"
              >
                <i class="fas fa-download me-2"></i>
                Descargar Muestra Gratis
              </button>
            </div>

            <!-- Garantía -->
            <div class="guarantee-notice">
              <i class="fas fa-shield-alt me-2"></i>
              <span>Garantía de satisfacción de 30 días o tu dinero de vuelta</span>
            </div>
          </div>
        </div>

        <!-- Imagen del eBook -->
        <div class="col-lg-6 order-lg-2 order-1 text-center mb-5 mb-lg-0">
          <div class="ebook-showcase">
            <div class="ebook-mockup card-modern">
              <div class="ebook-cover">
                <div class="cover-content">
                  <!-- Header con logo -->
                  <div class="cover-header mb-4">
                    <div class="logo-badge">
                      <i class="fas fa-book-open"></i>
                    </div>
                  </div>
                  
                  <!-- Título principal -->
                  <div class="cover-main-content">
                    <h2 class="cover-title">MARKETING<br><span class="title-accent">DIGITAL</span></h2>
                    <div class="title-underline"></div>
                    <p class="cover-subtitle">La Guía Definitiva para<br>Generar Ingresos Online</p>
                  </div>
                  
                  <!-- Features destacadas -->
                  <div class="cover-features">
                    <div class="feature-badge">200+ Páginas</div>
                    <div class="feature-badge">15 Plantillas</div>
                    <div class="feature-badge">Casos Reales</div>
                  </div>
                  
                  <!-- Autor -->
                  <div class="cover-footer">
                    <div class="author-info">
                      <span class="author-label">POR</span>
                      <span class="author-name">JUAN PÉREZ</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            
            <!-- Elementos decorativos -->
            <div class="floating-elements">
              <div class="floating-icon floating-icon-1">
                <i class="fas fa-chart-line"></i>
              </div>
              <div class="floating-icon floating-icon-2">
                <i class="fas fa-dollar-sign"></i>
              </div>
              <div class="floating-icon floating-icon-3">
                <i class="fas fa-rocket"></i>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Indicador de scroll -->
    <div class="scroll-indicator">
      <a href="#features" class="scroll-down">
        <i class="fas fa-chevron-down"></i>
      </a>
    </div>
  </section>
</template>

<style scoped>
/* Hero Section - Diseño limpio y profesional */
.hero-section {
  background-color: #f9f9f9;
  color: var(--text-primary);
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.hero-content {
  position: relative;
  z-index: 2;
}

/* Tipografía moderna */
.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 1.1;
  color: var(--text-primary);
  margin-bottom: 1.5rem;
}

.hero-subtitle {
  font-size: 1.25rem;
  color: var(--text-secondary);
  line-height: 1.6;
  font-weight: 400;
}

.highlight {
  color: var(--primary-color);
  font-weight: 600;
}

/* Lista de beneficios moderna */
.benefits-list {
  background: var(--bg-primary);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-xl);
  padding: 2rem;
  margin-bottom: 2rem;
}

.benefit-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
  font-weight: 500;
  color: var(--text-primary);
}

.benefit-item:last-child {
  margin-bottom: 0;
}

.benefit-icon {
  width: 1.5rem;
  height: 1.5rem;
  background-color: var(--primary-color);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 0.75rem;
  flex-shrink: 0;
}

/* Botones de acción */
.hero-buttons {
  margin-bottom: 2rem;
}

.hero-buttons .btn {
  padding: 1rem 2rem;
  font-weight: 500;
  border-radius: var(--radius-lg);
  transition: all 0.2s ease;
}

/* Garantía */
.guarantee-notice {
  display: flex;
  align-items: center;
  padding: 1rem 1.5rem;
  background: var(--bg-primary);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-lg);
  color: var(--text-secondary);
  font-size: 0.875rem;
}

.guarantee-notice i {
  color: var(--primary-color);
  font-size: 1rem;
}

/* eBook Mockup - Diseño moderno y profesional */
.ebook-showcase {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.ebook-mockup {
  width: 340px;
  height: 440px;
  background: var(--bg-secondary);
  border-radius: var(--radius-xl);
  box-shadow: 
    0 25px 50px -12px rgba(0, 0, 0, 0.25),
    0 0 0 1px rgba(0, 0, 0, 0.05);
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
  transform: perspective(1000px) rotateY(-5deg) rotateX(2deg);
}

.ebook-mockup:hover {
  transform: perspective(1000px) rotateY(0deg) rotateX(0deg) translateY(-10px);
  box-shadow: 
    0 35px 60px -12px rgba(0, 0, 0, 0.3),
    0 0 0 1px rgba(0, 0, 0, 0.05);
}

.ebook-cover {
  width: 100%;
  height: 100%;
  background: var(--bg-secondary);
  color: var(--text-primary);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  padding: 2rem;
}

/* Diseño de la portada profesional */
.cover-content {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  text-align: center;
  position: relative;
}

.cover-header {
  display: flex;
  justify-content: center;
  margin-bottom: 1rem;
}

.logo-badge {
  width: 3rem;
  height: 3rem;
  background: var(--primary-color);
  border-radius: var(--radius-md);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.25rem;
}

.cover-main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 2rem 0;
}

.cover-title {
  font-size: 2.25rem;
  font-weight: 900;
  line-height: 0.9;
  margin-bottom: 1rem;
  color: var(--text-primary);
  letter-spacing: -0.02em;
}

.title-accent {
  color: var(--primary-color);
  display: block;
}

.title-underline {
  width: 60px;
  height: 4px;
  background: var(--primary-color);
  margin: 1rem auto;
  border-radius: 2px;
}

.cover-subtitle {
  font-size: 0.875rem;
  color: var(--text-secondary);
  line-height: 1.4;
  font-weight: 500;
  margin-bottom: 0;
}

.cover-features {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin: 1.5rem 0;
}

.feature-badge {
  background: var(--bg-primary);
  border: 1px solid var(--border-light);
  padding: 0.5rem 1rem;
  border-radius: var(--radius-lg);
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.cover-footer {
  border-top: 1px solid var(--border-light);
  padding-top: 1rem;
}

.author-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.25rem;
}

.author-label {
  font-size: 0.625rem;
  color: var(--text-muted);
  font-weight: 500;
  letter-spacing: 1px;
  text-transform: uppercase;
}

.author-name {
  font-size: 0.875rem;
  color: var(--text-primary);
  font-weight: 700;
  letter-spacing: 0.5px;
}

/* Elementos flotantes decorativos */
.floating-elements {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: -1;
}

.floating-icon {
  position: absolute;
  width: 2.5rem;
  height: 2.5rem;
  background: var(--bg-secondary);
  border: 1px solid var(--border-light);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--primary-color);
  font-size: 1rem;
  box-shadow: var(--shadow-md);
  animation: float 6s ease-in-out infinite;
}

.floating-icon-1 {
  top: 20%;
  right: -1rem;
  animation-delay: 0s;
}

.floating-icon-2 {
  bottom: 30%;
  left: -1rem;
  animation-delay: 2s;
}

.floating-icon-3 {
  top: 60%;
  right: -0.5rem;
  animation-delay: 4s;
}

@keyframes float {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-10px) rotate(5deg); }
}

/* Indicador de scroll limpio */
.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
}

.scroll-down {
  width: 2.5rem;
  height: 2.5rem;
  background: var(--bg-secondary);
  border: 1px solid var(--border-light);
  border-radius: 50%;
  color: var(--text-secondary);
  text-decoration: none;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1rem;
  transition: all 0.2s ease;
  animation: bounce 2s infinite;
}

.scroll-down:hover {
  background: var(--primary-color);
  color: white;
  border-color: var(--primary-color);
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
  40% { transform: translateY(-8px); }
  60% { transform: translateY(-4px); }
}

/* Responsive */
@media (max-width: 991px) {
  .hero-section {
    min-height: auto;
    padding: 2rem 0;
  }
  
  .hero-title {
    font-size: 2.5rem;
    text-align: center;
  }
  
  .hero-subtitle {
    font-size: 1.125rem;
    text-align: center;
  }
  
  .ebook-mockup {
    width: 300px;
    height: 380px;
    transform: none;
    margin: 0 auto 2rem;
  }
  
  .ebook-mockup:hover {
    transform: translateY(-5px);
  }
  
  .cover-title {
    font-size: 2rem;
  }
  
  .hero-buttons {
    text-align: center;
  }
  
  .hero-buttons .btn {
    width: 100%;
    margin-bottom: 1rem;
    margin-right: 0 !important;
  }
  
  .benefits-list {
    padding: 1.5rem;
  }
  
  .floating-elements {
    display: none;
  }
  
  .guarantee-notice {
    text-align: center;
    justify-content: center;
  }
}

@media (max-width: 768px) {
  .hero-section {
    padding: 1.5rem 0;
  }
  
  .hero-title {
    font-size: 2.2rem;
    line-height: 1.2;
    margin-bottom: 1rem;
  }
  
  .hero-subtitle {
    font-size: 1.1rem;
    margin-bottom: 2rem;
  }
  
  .ebook-mockup {
    width: 280px;
    height: 360px;
  }
  
  .cover-title {
    font-size: 1.8rem;
  }
  
  .cover-subtitle {
    font-size: 0.8rem;
  }
  
  .benefits-list {
    padding: 1.25rem;
    margin-bottom: 2rem;
  }
  
  .benefit-item {
    font-size: 0.95rem;
    gap: 0.75rem;
  }
  
  .hero-buttons .btn {
    padding: 0.875rem 1.5rem;
    font-size: 0.95rem;
  }
  
  .guarantee-notice {
    font-size: 0.8rem;
    padding: 0.875rem 1.25rem;
    flex-direction: column;
    gap: 0.5rem;
  }
  
  .guarantee-notice i {
    font-size: 1.2rem;
  }
}

@media (max-width: 575px) {
    .hero-section {
        padding: 1rem 0;
    }
  
  .hero-title {
    font-size: 1.75rem;
    line-height: 1.2;
  }
  
  .hero-subtitle {
    font-size: 1rem;
  }
  
  .ebook-mockup {
    height: 510px;
    margin-bottom: 1.5rem;
    box-shadow: none;
    border: none;
    border-radius: 0;
    transform: none;
  }
  
  .ebook-cover {
    padding: 1.5rem;
    background-color: #f9f9f9;
  }
  
  .cover-title {
    font-size: 1.5rem;
  }
  
  .cover-subtitle {
    font-size: 0.75rem;
    line-height: 1.3;
  }
  
  .logo-badge {
    width: 25.25rem;
    height: 10.25rem;
    font-size: 5.95rem;
  }
  
  
  
  .cover-main-content {
    margin: 1.5rem 0;
  }
  
  .cover-features {
    margin: 1rem 0;
    gap: 0.4rem;
  }
  
  .feature-badge {
    font-size: 0.65rem;
    padding: 0.35rem 0.7rem;
    letter-spacing: 0.25px;
  }
  
  .author-label {
    font-size: 0.55rem;
  }
  
  .author-name {
    font-size: 0.8rem;
  }
  
  .benefits-list {
    padding: 1rem;
    margin-bottom: 1.5rem;
  }
  
  .benefit-item {
    font-size: 0.9rem;
    gap: 0.75rem;
    margin-bottom: 0.875rem;
  }
  
  .benefit-icon {
    width: 1.25rem;
    height: 1.25rem;
    font-size: 0.7rem;
  }
  
  .hero-buttons {
    margin-bottom: 1.5rem;
  }
  
  .hero-buttons .btn {
    padding: 0.75rem 1.25rem;
    font-size: 0.9rem;
    margin-bottom: 0.75rem;
  }
  
  .guarantee-notice {
    font-size: 0.75rem;
    padding: 0.75rem 1rem;
    text-align: center;
    flex-direction: column;
    gap: 0.4rem;
  }
  
  .guarantee-notice span {
    text-align: center;
  }
  
  .scroll-indicator {
    bottom: 1rem;
  }
  
  .scroll-down {
    width: 2rem;
    height: 2rem;
    font-size: 0.875rem;
  }
}

@media (max-width: 380px) {
  .hero-title {
    font-size: 1.6rem;
  }
  
  .hero-subtitle {
    font-size: 0.95rem;
  }
  
  .ebook-mockup {
    width: 220px;
    height: 285px;
  }
  
  .cover-title {
    font-size: 1.35rem;
  }
  
  .cover-subtitle {
    font-size: 0.7rem;
  }
  
  .logo-badge {
    width: 2rem;
    height: 2rem;
    font-size: 0.875rem;
  }
  
  .benefits-list {
    padding: 0.875rem;
  }
  
  .benefit-item {
    font-size: 0.85rem;
  }
  
  .hero-buttons .btn {
    padding: 0.7rem 1rem;
    font-size: 0.85rem;
  }
  
  .guarantee-notice {
    font-size: 0.7rem;
    padding: 0.7rem 0.875rem;
  }
}
</style>
