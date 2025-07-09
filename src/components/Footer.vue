<script setup>
import { ref } from 'vue'

const currentYear = ref(new Date().getFullYear())

const socialLinks = ref([
  {
    name: 'Facebook',
    icon: 'fab fa-facebook-f',
    url: 'https://facebook.com',
    color: '#1877F2'
  },
  {
    name: 'Twitter',
    icon: 'fab fa-twitter',
    url: 'https://twitter.com',
    color: '#1DA1F2'
  },
  {
    name: 'Instagram',
    icon: 'fab fa-instagram',
    url: 'https://instagram.com',
    color: '#E4405F'
  },
  {
    name: 'LinkedIn',
    icon: 'fab fa-linkedin-in',
    url: 'https://linkedin.com',
    color: '#0A66C2'
  },
  {
    name: 'YouTube',
    icon: 'fab fa-youtube',
    url: 'https://youtube.com',
    color: '#FF0000'
  }
])

const quickLinks = ref([
  { name: 'Inicio', href: '#hero' },
  { name: 'Características', href: '#features' },
  { name: 'Sobre el Autor', href: '#author' },
  { name: 'Testimonios', href: '#testimonials' },
  { name: 'Precios', href: '#pricing' }
])

const legalLinks = ref([
  { name: 'Política de Privacidad', href: '#' },
  { name: 'Términos y Condiciones', href: '#' },
  { name: 'Política de Reembolso', href: '#' },
  { name: 'Contacto', href: 'mailto:contacto@ebook.com' }
])

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<template>
  <footer class="footer bg-dark text-light">
    <!-- Sección principal del footer -->
    <div class="footer-main section-padding">
      <div class="container">
        <div class="row">
          <!-- Información de la empresa -->
          <div class="col-lg-4 col-md-6 mb-4">
            <div class="footer-section">
              <h5 class="footer-title mb-4">
                <i class="fas fa-book-open me-2 text-danger"></i>
                eBook Pro
              </h5>
              
              <p class="footer-description mb-4">
                Transformando emprendedores en expertos de marketing digital. 
                Más de 5,000 estudiantes han revolucionado sus negocios con 
                nuestras estrategias probadas.
              </p>

              <!-- Estadísticas rápidas -->
              <div class="footer-stats">
                <div class="row">
                  <div class="col-6">
                    <div class="stat-item mb-3">
                      <div class="stat-number text-danger fw-bold">5,000+</div>
                      <div class="stat-label small">Estudiantes</div>
                    </div>
                  </div>
                  <div class="col-6">
                    <div class="stat-item mb-3">
                      <div class="stat-number text-danger fw-bold">4.9★</div>
                      <div class="stat-label small">Calificación</div>
                    </div>
                  </div>
                </div>
              </div>

              <!-- Redes sociales -->
              <div class="social-links">
                <h6 class="small fw-bold text-uppercase mb-3">Síguenos</h6>
                <div class="d-flex gap-2">
                  <a 
                    v-for="social in socialLinks" 
                    :key="social.name"
                    :href="social.url"
                    :title="social.name"
                    class="social-link"
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    <i :class="social.icon"></i>
                  </a>
                </div>
              </div>
            </div>
          </div>

          <!-- Enlaces rápidos -->
          <div class="col-lg-2 col-md-6 mb-4">
            <div class="footer-section">
              <h6 class="footer-title text-uppercase mb-4">Enlaces Rápidos</h6>
              <ul class="footer-links">
                <li v-for="link in quickLinks" :key="link.name" class="mb-2">
                  <a :href="link.href" class="footer-link">
                    <i class="fas fa-chevron-right me-2 small"></i>
                    {{ link.name }}
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <!-- Información legal -->
          <div class="col-lg-3 col-md-6 mb-4">
            <div class="footer-section">
              <h6 class="footer-title text-uppercase mb-4">Legal & Soporte</h6>
              <ul class="footer-links">
                <li v-for="link in legalLinks" :key="link.name" class="mb-2">
                  <a :href="link.href" class="footer-link">
                    <i class="fas fa-chevron-right me-2 small"></i>
                    {{ link.name }}
                  </a>
                </li>
              </ul>
              
              <!-- Información de contacto -->
              <div class="contact-info mt-4">
                <div class="contact-item mb-2">
                  <i class="fas fa-envelope me-2"></i>
                  <a href="mailto:contacto@ebook.com" class="footer-link">
                    contacto@ebook.com
                  </a>
                </div>
                <div class="contact-item mb-2">
                  <i class="fas fa-clock me-2"></i>
                  <span class="small">Respuesta en 24hrs</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Newsletter y CTA -->
          <div class="col-lg-3 col-md-6 mb-4">
            <div class="footer-section">
              <h6 class="footer-title text-uppercase mb-4">Mantente Actualizado</h6>
              
              <p class="small mb-3">
                Recibe tips exclusivos y ofertas especiales directamente en tu email.
              </p>

              <!-- Mini newsletter signup -->
              <div class="footer-newsletter mb-4">
                <div class="input-group">
                  <input 
                    type="email" 
                    class="form-control form-control-sm" 
                    placeholder="Tu email..."
                  >
                  <button class="btn btn-danger btn-sm" type="button">
                    <i class="fas fa-paper-plane"></i>
                  </button>
                </div>
                <small class="d-block mt-2">
                  <i class="fas fa-shield-alt me-1"></i>
                  No spam, solo contenido valioso
                </small>
              </div>

              <!-- Botón principal -->
              <a 
                href="#pricing" 
                class="btn btn-custom-danger btn-sm w-100"
              >
                <i class="fas fa-shopping-cart me-2"></i>
                Obtener eBook Ahora
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Línea divisoria -->
    <div class="footer-divider">
      <div class="container">
        <hr class="border-secondary">
      </div>
    </div>

    <!-- Footer bottom -->
    <div class="footer-bottom py-4">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-md-6 text-center text-md-start">
            <p class="mb-0 small">
              © {{ currentYear }} eBook Pro. Todos los derechos reservados.
            </p>
          </div>
          
          <div class="col-md-6 text-center text-md-end">
            <div class="footer-badges d-flex justify-content-center justify-content-md-end align-items-center gap-3">
              <!-- Badges de confianza -->
              <div class="trust-badge">
                <i class="fas fa-shield-alt text-success me-1"></i>
                <span class="small">Pago Seguro</span>
              </div>
              
              <div class="trust-badge">
                <i class="fas fa-undo text-info me-1"></i>
                <span class="small">30 días garantía</span>
              </div>
              
              <!-- Botón volver arriba -->
              <button 
                @click="scrollToTop"
                class="btn-scroll-top"
                title="Volver arriba"
              >
                <i class="fas fa-chevron-up"></i>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: var(--text-primary);
  color: var(--bg-primary);
  border-top: 1px solid var(--border-light);
}

.footer-main {
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-title {
  color: white;
  font-weight: 600;
  position: relative;
  margin-bottom: 1.5rem;
}

.footer-title::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 0;
  width: 40px;
  height: 2px;
  background: var(--primary-color);
  border-radius: 1px;
}

.footer-description {
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.6;
  font-size: 0.875rem;
}

.footer-stats .stat-number {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--primary-color);
}

.footer-stats .stat-label {
  color: rgba(255, 255, 255, 0.6);
  font-size: 0.75rem;
}

.social-links .social-link {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: var(--radius-md);
  background: rgba(255, 255, 255, 0.1);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  transition: all 0.2s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
  font-size: 0.875rem;
}

.social-link:hover {
  background: var(--primary-color);
  color: white;
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
  border-color: var(--primary-color);
}

.footer-links {
  list-style: none;
  padding: 0;
}

.footer-link {
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  transition: all 0.2s ease;
  font-size: 0.875rem;
  display: flex;
  align-items: center;
  padding: 0.25rem 0;
}

.footer-link:hover {
  color: var(--primary-color);
  padding-left: 0.5rem;
}

.footer-link i {
  transition: all 0.2s ease;
  font-size: 0.75rem;
  opacity: 0.6;
}

.footer-link:hover i {
  color: var(--primary-color);
  opacity: 1;
}

.contact-info .contact-item {
  display: flex;
  align-items: center;
  color: rgba(255, 255, 255, 0.8);
  font-size: 0.875rem;
  margin-bottom: 0.5rem;
}

.contact-item i {
  color: var(--primary-color);
  margin-right: 0.5rem;
  font-size: 0.875rem;
}

.footer-newsletter .form-control {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: white;
  border-radius: var(--radius-md);
  font-size: 0.875rem;
}

.footer-newsletter .form-control::placeholder {
  color: rgba(255, 255, 255, 0.6);
}

.footer-newsletter .form-control:focus {
  background: rgba(255, 255, 255, 0.15);
  border-color: var(--primary-color);
  box-shadow: 0 0 0 0.2rem rgba(59, 130, 246, 0.25);
  color: white;
}

.footer-newsletter .btn {
  border-radius: var(--radius-md);
}

.footer-divider {
  opacity: 0.3;
}

.footer-bottom {
  background: rgba(0, 0, 0, 0.2);
}

.trust-badge {
  display: flex;
  align-items: center;
  color: rgba(255, 255, 255, 0.8);
  font-size: 0.75rem;
  gap: 0.25rem;
}

.btn-scroll-top {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: var(--radius-md);
  background: var(--primary-color);
  color: white;
  border: none;
  transition: all 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.875rem;
}

.btn-scroll-top:hover {
  background: var(--secondary-color);
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}

/* Animaciones */
.footer-section {
  animation: fadeInUp 0.6s ease-out;
}

.footer-section:nth-child(1) { animation-delay: 0.1s; }
.footer-section:nth-child(2) { animation-delay: 0.2s; }
.footer-section:nth-child(3) { animation-delay: 0.3s; }
.footer-section:nth-child(4) { animation-delay: 0.4s; }

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive */
@media (max-width: 768px) {
  .footer-title::after {
    width: 30px;
  }
  
  .social-links .d-flex {
    justify-content: center;
  }
  
  .footer-newsletter {
    text-align: center;
  }
  
  .footer-badges {
    flex-direction: column;
    gap: 1rem;
  }
  
  .trust-badge {
    justify-content: center;
  }
  
  .footer-stats .row {
    text-align: center;
  }
}

@media (max-width: 575px) {
  .footer-main {
    padding: 3rem 0;
  }
  
  .footer-section {
    text-align: center;
    margin-bottom: 2rem;
  }
  
  .footer-links {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .contact-info {
    text-align: center;
  }
  
  .contact-item {
    justify-content: center;
  }
}

/* Estados hover mejorados */
.footer-link:hover,
.social-link:hover,
.btn-scroll-top:hover {
  animation: pulse 0.2s ease-in-out;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.02); }
  100% { transform: scale(1); }
}
</style>
