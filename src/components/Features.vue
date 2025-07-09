<script setup>
import { ref } from 'vue'

const features = ref([
  {
    icon: 'fas fa-rocket',
    title: 'Estrategias Comprobadas',
    description: 'Métodos probados por expertos que han generado millones en ventas online. Aprende técnicas que realmente funcionan.',
    color: 'text-danger'
  },
  {
    icon: 'fas fa-chart-line',
    title: 'Resultados Medibles',
    description: 'Sistema completo de métricas y KPIs para medir el ROI de cada campaña. Incluye dashboards y plantillas.',
    color: 'text-danger'
  },
  {
    icon: 'fas fa-users',
    title: 'Casos de Estudio Reales',
    description: '15+ casos de estudio detallados de empresas que aumentaron sus ventas en +300% usando estas estrategias.',
    color: 'text-danger'
  },
  {
    icon: 'fas fa-tools',
    title: 'Herramientas Incluidas',
    description: 'Pack completo con plantillas, checklists, calculadoras y herramientas que necesitas para implementar todo.',
    color: 'text-danger'
  }
])
</script>

<template>
  <section id="features" class="section-padding bg-light">
    <div class="container">
      <!-- Título de la sección -->
      <div class="row">
        <div class="col-lg-8 mx-auto text-center mb-5">
          <span class="badge bg-danger mb-3 px-3 py-2">
            ¿Qué vas a aprender?
          </span>
          <h2 class="display-5 fw-bold mb-4">
            Todo lo que necesitas para triunfar en 
            <span class="text-danger">Marketing Digital</span>
          </h2>
          <p class="lead text-muted">
            Un sistema completo y probado que te llevará desde cero hasta generar 
            ingresos consistentes con marketing digital
          </p>
        </div>
      </div>

      <!-- Grid de características -->
      <div class="row g-4">
        <div 
          v-for="(feature, index) in features" 
          :key="index"
          class="col-lg-6"
        >
          <div class="feature-card h-100 p-4 custom-shadow-hover">
            <div class="feature-icon mb-4">
              <i :class="[feature.icon, feature.color]"></i>
            </div>
            
            <h4 class="fw-bold mb-3">{{ feature.title }}</h4>
            <p class="text-muted mb-4">{{ feature.description }}</p>
            
            <div class="feature-highlight">
              <small class="text-danger fw-semibold">
                <i class="fas fa-check-circle me-1"></i>
                Implementación paso a paso incluida
              </small>
            </div>
          </div>
        </div>
      </div>

      <!-- Sección de beneficios adicionales -->
      <div class="row mt-5">
        <div class="col-lg-10 mx-auto">
          <div class="benefits-box p-5 rounded-3 custom-shadow">
            <div class="row align-items-center">
              <div class="col-md-8">
                <h3 class="fw-bold mb-3 text-danger">
                  <i class="fas fa-gift me-2"></i>
                  Bonos Exclusivos Incluidos
                </h3>
                <div class="row">
                  <div class="col-sm-6">
                    <div class="bonus-item mb-3">
                      <i class="fas fa-video text-danger me-2"></i>
                      <span>5 horas de video tutoriales</span>
                    </div>
                    <div class="bonus-item mb-3">
                      <i class="fas fa-file-excel text-danger me-2"></i>
                      <span>15 plantillas descargables</span>
                    </div>
                  </div>
                  <div class="col-sm-6">
                    <div class="bonus-item mb-3">
                      <i class="fas fa-users text-danger me-2"></i>
                      <span>Acceso a comunidad privada</span>
                    </div>
                    <div class="bonus-item mb-3">
                      <i class="fas fa-sync text-danger me-2"></i>
                      <span>Actualizaciones de por vida</span>
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-md-4 text-center">
                <div class="bonus-value">
                  <span class="text-muted text-decoration-line-through fs-4">$297</span>
                  <div class="text-danger fw-bold fs-2">GRATIS</div>
                  <small class="text-muted">con tu compra</small>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Estadísticas -->
      <div class="row mt-5">
        <div class="col-lg-12">
          <div class="stats-container p-4 rounded-3">
            <div class="row text-center">
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-number text-danger fw-bold">5,000+</div>
                  <div class="stat-label text-muted">Estudiantes</div>
                </div>
              </div>
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-number text-danger fw-bold">200+</div>
                  <div class="stat-label text-muted">Páginas</div>
                </div>
              </div>
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-number text-danger fw-bold">4.9★</div>
                  <div class="stat-label text-muted">Calificación</div>
                </div>
              </div>
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-number text-danger fw-bold">98%</div>
                  <div class="stat-label text-muted">Satisfacción</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.feature-card {
  background: white;
  border-radius: 15px;
  border: 1px solid #e9ecef;
  transition: all 0.3s ease;
  height: 100%;
}

.feature-card:hover {
  border-color: var(--secondary-color);
}

.feature-icon i {
  font-size: 3rem;
  opacity: 0.8;
}

.feature-highlight {
  padding-top: 1rem;
  border-top: 1px solid #e9ecef;
}

.benefits-box {
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  border: 1px solid #dee2e6;
}

.bonus-item {
  display: flex;
  align-items: center;
  font-weight: 500;
}

.bonus-item i {
  font-size: 1.1rem;
}

.bonus-value {
  padding: 1rem;
  background: white;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.stats-container {
  background: black;
  color: white;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: white !important;
}

.stat-label {
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.8) !important;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.stat-item {
  padding: 1rem;
}

/* Animaciones */
.feature-card {
  animation: fadeInUp 0.6s ease-out;
}

.feature-card:nth-child(1) { animation-delay: 0.1s; }
.feature-card:nth-child(2) { animation-delay: 0.2s; }
.feature-card:nth-child(3) { animation-delay: 0.3s; }
.feature-card:nth-child(4) { animation-delay: 0.4s; }

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive */
@media (max-width: 768px) {
  .feature-icon i {
    font-size: 2.5rem;
  }
  
  .stat-number {
    font-size: 2rem;
  }
  
  .benefits-box {
    text-align: center;
  }
  
  .bonus-value {
    margin-top: 2rem;
  }
}
</style>
