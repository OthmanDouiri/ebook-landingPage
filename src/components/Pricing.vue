<script setup>
import { ref } from 'vue'

const isLoading = ref(false)

// URLs de ejemplo para integración de pagos
const gumroadUrl = 'https://gumroad.com/l/your-ebook'  // Reemplazar con tu URL real
const paypalUrl = 'https://paypal.me/your-paypal'      // Reemplazar con tu URL real

const handlePurchase = async (platform) => {
  isLoading.value = true
  
  // Tracking del evento de compra (Google Analytics, Facebook Pixel, etc.)
  // gtag('event', 'purchase_intent', {
  //   'event_category': 'ecommerce',
  //   'event_label': platform
  // })
  
  setTimeout(() => {
    if (platform === 'gumroad') {
      window.open(gumroadUrl, '_blank')
    } else if (platform === 'paypal') {
      window.open(paypalUrl, '_blank')
    }
    isLoading.value = false
  }, 1000)
}

const scrollToEmail = () => {
  document.getElementById('email-capture').scrollIntoView({ behavior: 'smooth' })
}

// Contador de tiempo limitado (ejemplo)
const timeLeft = ref({
  hours: 23,
  minutes: 45,
  seconds: 30
})

// Simulación de contador regresivo
setInterval(() => {
  if (timeLeft.value.seconds > 0) {
    timeLeft.value.seconds--
  } else if (timeLeft.value.minutes > 0) {
    timeLeft.value.minutes--
    timeLeft.value.seconds = 59
  } else if (timeLeft.value.hours > 0) {
    timeLeft.value.hours--
    timeLeft.value.minutes = 59
    timeLeft.value.seconds = 59
  }
}, 1000)
</script>

<template>
  <section id="pricing" class="section-padding section-light">
    <div class="container">
      <!-- Título de la sección -->
      <div class="row">
        <div class="col-lg-8 mx-auto text-center mb-5">
          <span class="badge bg-danger mb-3 px-3 py-2">
            <i class="fas fa-fire me-1"></i>
            Oferta Especial por Tiempo Limitado
          </span>
          <h2 class="display-5 fw-bold mb-4">
            Invierte en tu <span class="text-danger">Futuro Digital</span>
          </h2>
          <p class="lead text-muted">
            Todo lo que necesitas para dominar el marketing digital y generar ingresos consistentes
          </p>
        </div>
      </div>

      <!-- Contador regresivo -->
      <div class="row mb-5">
        <div class="col-lg-8 mx-auto">
          <div class="countdown-container text-center p-4 rounded-3 custom-shadow">
            <h5 class="fw-bold text-danger mb-3">
              <i class="fas fa-clock me-2"></i>
              ¡Oferta termina pronto!
            </h5>
            <div class="countdown d-flex justify-content-center gap-3">
              <div class="time-unit">
                <div class="time-value">{{ String(timeLeft.hours).padStart(2, '0') }}</div>
                <div class="time-label">Horas</div>
              </div>
              <div class="time-separator">:</div>
              <div class="time-unit">
                <div class="time-value">{{ String(timeLeft.minutes).padStart(2, '0') }}</div>
                <div class="time-label">Minutos</div>
              </div>
              <div class="time-separator">:</div>
              <div class="time-unit">
                <div class="time-value">{{ String(timeLeft.seconds).padStart(2, '0') }}</div>
                <div class="time-label">Segundos</div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Planes de precios -->
      <div class="row justify-content-center">
        <!-- Plan Básico (Lead Magnet) -->
        <div class="col-lg-4 col-md-6 mb-4">
          <div class="pricing-card h-100 p-4 rounded-3 custom-shadow-hover">
            <div class="card-header text-center mb-4">
              <div class="plan-icon mb-3">
                <i class="fas fa-download fa-2x text-danger"></i>
              </div>
              <h4 class="fw-bold">Muestra Gratuita</h4>
              <p class="text-muted">Perfecto para empezar</p>
            </div>

            <div class="price-section text-center mb-4">
              <div class="price">
                <span class="currency">$</span>
                <span class="amount">0</span>
              </div>
              <p class="price-description text-muted">Descarga instantánea</p>
            </div>

            <div class="features-list mb-4">
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Primer capítulo completo (20 páginas)</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Guía de implementación rápida</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>1 plantilla descargable</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Acceso a newsletter semanal</span>
              </div>
            </div>

            <button 
              @click="scrollToEmail"
              class="btn btn-outline-danger w-100 btn-lg"
            >
              <i class="fas fa-download me-2"></i>
              Descargar Gratis
            </button>
          </div>
        </div>

        <!-- Plan Principal (Más Popular) -->
        <div class="col-lg-4 col-md-6 mb-4">
          <div class="pricing-card featured h-100 p-4 rounded-3 custom-shadow-hover">
            <div class="popular-badge">
              <span class="badge bg-danger text-white">
                <i class="fas fa-crown me-1"></i>
                Más Popular
              </span>
            </div>

            <div class="card-header text-center mb-4">
              <div class="plan-icon mb-3">
                <i class="fas fa-rocket fa-2x text-danger"></i>
              </div>
              <h4 class="fw-bold">eBook Completo</h4>
              <p class="text-muted">La guía definitiva</p>
            </div>

            <div class="price-section text-center mb-4">
              <div class="original-price">
                <span class="text-muted text-decoration-line-through">$97</span>
              </div>
              <div class="price">
                <span class="currency">$</span>
                <span class="amount">47</span>
              </div>
              <p class="price-description text-danger fw-bold">¡50% de descuento!</p>
            </div>

            <div class="features-list mb-4">
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span><strong>200+ páginas</strong> de contenido premium</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span><strong>15 plantillas</strong> y herramientas</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span><strong>5 horas</strong> de video tutoriales</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Casos de estudio reales</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Acceso a comunidad privada</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Actualizaciones de por vida</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span><strong>Bonus:</strong> Calculadora ROI</span>
              </div>
            </div>

            <div class="purchase-buttons">
              <button 
                @click="handlePurchase('gumroad')"
                :disabled="isLoading"
                class="btn btn-custom-primary w-100 btn-lg mb-3"
              >
                <span v-if="!isLoading">
                  <i class="fas fa-shopping-cart me-2"></i>
                  Comprar con Gumroad
                </span>
                <span v-else>
                  <i class="fas fa-spinner fa-spin me-2"></i>
                  Redirigiendo...
                </span>
              </button>

              <button 
                @click="handlePurchase('paypal')"
                :disabled="isLoading"
                class="btn btn-custom-secondary w-100"
              >
                <i class="fab fa-paypal me-2"></i>
                Pagar con PayPal
              </button>
            </div>
          </div>
        </div>

        <!-- Plan Premium -->
        <div class="col-lg-4 col-md-6 mb-4">
          <div class="pricing-card h-100 p-4 rounded-3 custom-shadow-hover">
            <div class="card-header text-center mb-4">
              <div class="plan-icon mb-3">
                <i class="fas fa-crown fa-2x text-danger"></i>
              </div>
              <h4 class="fw-bold">Paquete Premium</h4>
              <p class="text-muted">Para emprendedores serios</p>
            </div>

            <div class="price-section text-center mb-4">
              <div class="original-price">
                <span class="text-muted text-decoration-line-through">$297</span>
              </div>
              <div class="price">
                <span class="currency">$</span>
                <span class="amount">97</span>
              </div>
              <p class="price-description text-danger fw-bold">Incluye consultoría</p>
            </div>

            <div class="features-list mb-4">
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Todo del plan anterior</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span><strong>1 hora</strong> de consultoría 1:1</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Revisión de tu estrategia</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Plan personalizado de 90 días</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span>Soporte prioritario por email</span>
              </div>
              <div class="feature-item mb-2">
                <i class="fas fa-check text-danger me-2"></i>
                <span><strong>Bonus:</strong> Audit gratuito</span>
              </div>
            </div>

            <button 
              @click="handlePurchase('gumroad')"
              :disabled="isLoading"
              class="btn btn-dark w-100 btn-lg text-white fw-bold"
            >
              <i class="fas fa-star me-2"></i>
              Obtener Premium
            </button>
          </div>
        </div>
      </div>

      <!-- Garantía -->
      <div class="row mt-5">
        <div class="col-lg-8 mx-auto">
          <div class="guarantee-section p-5 rounded-3 custom-shadow text-center">
            <div class="guarantee-icon mb-4">
              <i class="fas fa-shield-alt fa-3x text-danger"></i>
            </div>
            <h3 class="fw-bold mb-3 text-danger">Garantía de 30 Días</h3>
            <p class="lead mb-4">
              Si no estás 100% satisfecho con el contenido, te devolvemos tu dinero. 
              Sin preguntas, sin complicaciones.
            </p>
            <div class="guarantee-features">
              <div class="row">
                <div class="col-md-4 mb-3">
                  <i class="fas fa-clock text-danger me-2"></i>
                  <span>30 días completos</span>
                </div>
                <div class="col-md-4 mb-3">
                  <i class="fas fa-thumbs-up text-danger me-2"></i>
                  <span>Sin preguntas</span>
                </div>
                <div class="col-md-4 mb-3">
                  <i class="fas fa-money-bill-wave text-danger me-2"></i>
                  <span>Reembolso completo</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- FAQ rápido -->
      <div class="row mt-5">
        <div class="col-lg-10 mx-auto">
          <h4 class="text-center fw-bold mb-4">Preguntas Frecuentes</h4>
          <div class="row">
            <div class="col-md-6 mb-3">
              <div class="faq-item p-3 rounded bg-white">
                <h6 class="fw-bold text-danger">¿Cómo recibo el eBook?</h6>
                <p class="text-muted small mb-0">
                  Inmediatamente después del pago recibirás un email con el enlace de descarga.
                </p>
              </div>
            </div>
            <div class="col-md-6 mb-3">
              <div class="faq-item p-3 rounded bg-white">
                <h6 class="fw-bold text-danger">¿En qué formato está?</h6>
                <p class="text-muted small mb-0">
                  PDF optimizado para lectura en cualquier dispositivo + videos MP4.
                </p>
              </div>
            </div>
            <div class="col-md-6 mb-3">
              <div class="faq-item p-3 rounded bg-white">
                <h6 class="fw-bold text-danger">¿Es para principiantes?</h6>
                <p class="text-muted small mb-0">
                  Sí, está diseñado para todos los niveles, desde principiantes hasta avanzados.
                </p>
              </div>
            </div>
            <div class="col-md-6 mb-3">
              <div class="faq-item p-3 rounded bg-white">
                <h6 class="fw-bold text-danger">¿Hay soporte incluido?</h6>
                <p class="text-muted small mb-0">
                  Acceso a comunidad privada donde podrás hacer preguntas y recibir ayuda.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.countdown-container {
  background: black;
  color: white;
  border: 1px solid #e9ecef;
}

.countdown {
  font-family: 'Courier New', monospace;
}

.time-unit {
  text-align: center;
  padding: 0.5rem;
}

.time-value {
  font-size: 2rem;
  font-weight: bold;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 8px;
  padding: 0.5rem 1rem;
  min-width: 60px;
}

.time-label {
  font-size: 0.8rem;
  margin-top: 0.5rem;
  opacity: 0.9;
}

.time-separator {
  font-size: 2rem;
  font-weight: bold;
  align-self: center;
  opacity: 0.7;
}

.pricing-card {
  background: white;
  border: 2px solid #e9ecef;
  transition: all 0.3s ease;
  position: relative;
}

.pricing-card:hover {
  border-color: var(--secondary-color);
  transform: translateY(-5px);
}

.pricing-card.featured {
  border-color: var(--primary-color);
  transform: scale(1.05);
  position: relative;
}

.popular-badge {
  position: absolute;
  top: -10px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 10;
}

.plan-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}

.pricing-card.featured .plan-icon {
  color: white;
}

.price {
  font-size: 3rem;
  font-weight: bold;
  color: var(--primary-color);
  line-height: 1;
}

.currency {
  font-size: 1.5rem;
  vertical-align: top;
}

.original-price {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.features-list {
  min-height: 250px;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  font-size: 0.95rem;
}

.feature-item i {
  margin-top: 0.2rem;
  font-size: 0.9rem;
}

.purchase-buttons button {
  transition: all 0.3s ease;
}

.guarantee-section {
  background: linear-gradient(135deg, #e8f5e8 0%, #f0f8f0 100%);
  border: 1px solid #d4edda;
}

.guarantee-icon {
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.1); }
  100% { transform: scale(1); }
}

.faq-item {
  border: 1px solid #e9ecef;
  transition: all 0.3s ease;
}

.faq-item:hover {
  border-color: var(--primary-color);
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

/* Animaciones */
.pricing-card {
  animation: slideInUp 0.6s ease-out;
}

.pricing-card:nth-child(1) { animation-delay: 0.1s; }
.pricing-card:nth-child(2) { animation-delay: 0.2s; }
.pricing-card:nth-child(3) { animation-delay: 0.3s; }

@keyframes slideInUp {
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
@media (max-width: 991px) {
  .pricing-card.featured {
    transform: none;
    margin-bottom: 2rem;
  }
  
  .time-value {
    font-size: 1.5rem;
    min-width: 50px;
    padding: 0.3rem 0.8rem;
  }
  
  .time-separator {
    font-size: 1.5rem;
  }
}

@media (max-width: 768px) {
  .price {
    font-size: 2.5rem;
  }
  
  .countdown {
    flex-direction: column;
    gap: 1rem;
  }
  
  .time-separator {
    display: none;
  }
  
  .features-list {
    min-height: auto;
  }
  
  .guarantee-features .row {
    text-align: center;
  }
}

@media (max-width: 575px) {
  .pricing-card {
    padding: 2rem !important;
  }
  
  .plan-icon {
    width: 60px;
    height: 60px;
  }
  
  .plan-icon i {
    font-size: 1.5rem;
  }
  
  .countdown-container {
    padding: 2rem !important;
  }
}
</style>
