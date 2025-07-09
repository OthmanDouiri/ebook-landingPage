<script setup>
import { ref } from 'vue'

const testimonials = ref([
  {
    id: 1,
    name: 'María González',
    role: 'Emprendedora Digital',
    company: 'Tienda Online Fashion',
    avatar: 'fas fa-user-circle',
    rating: 5,
    text: 'En solo 3 meses aplicando las estrategias del eBook, mis ventas aumentaron un 400%. Las técnicas son súper prácticas y fáciles de implementar. ¡Totalmente recomendado!',
    result: '+400% en ventas',
    timeframe: '3 meses'
  },
  {
    id: 2,
    name: 'Carlos Ruiz',
    role: 'Coach de Negocios',
    company: 'Business Growth',
    avatar: 'fas fa-user-tie',
    rating: 5,
    text: 'Como coach, siempre estoy buscando contenido de calidad para recomendar a mis clientes. Este eBook es una joya. Explica conceptos complejos de manera simple.',
    result: '50+ clientes ayudados',
    timeframe: '6 meses'
  },
  {
    id: 3,
    name: 'Ana Rodríguez',
    role: 'Fundadora Startup',
    company: 'Tech Solutions',
    avatar: 'fas fa-user-graduate',
    rating: 5,
    text: 'Estaba perdida con el marketing digital de mi startup. Este libro me dio la estructura y las herramientas que necesitaba. Ahora tengo un sistema que realmente funciona.',
    result: '$50K en funding',
    timeframe: '4 meses'
  },
  {
    id: 4,
    name: 'Luis Martínez',
    role: 'Freelancer',
    company: 'Consultor Marketing',
    avatar: 'fas fa-user-cog',
    rating: 5,
    text: 'Pasé de tener 2-3 clientes a tener una lista de espera. Las estrategias de posicionamiento y captación de leads son oro puro. Mejor inversión que he hecho.',
    result: '10x más clientes',
    timeframe: '5 meses'
  },
  {
    id: 5,
    name: 'Patricia Vega',
    role: 'Blogger',
    company: 'Lifestyle Blog',
    avatar: 'fas fa-user-edit',
    rating: 5,
    text: 'Mi blog pasó de 500 a 50,000 visitantes mensuales siguiendo las técnicas del eBook. Los métodos de SEO y content marketing son increíblemente efectivos.',
    result: '50K visitantes/mes',
    timeframe: '8 meses'
  },
  {
    id: 6,
    name: 'Roberto Silva',
    role: 'E-commerce Owner',
    company: 'Tech Store Online',
    avatar: 'fas fa-user-crown',
    rating: 5,
    text: 'Mi ROI en publicidad digital mejoró un 300% después de aplicar las estrategias. Ahora entiendo cómo optimizar campañas y reducir costos de adquisición.',
    result: '+300% ROI',
    timeframe: '2 meses'
  }
])

const currentTestimonial = ref(0)

const nextTestimonial = () => {
  currentTestimonial.value = (currentTestimonial.value + 1) % testimonials.value.length
}

const prevTestimonial = () => {
  currentTestimonial.value = currentTestimonial.value === 0 
    ? testimonials.value.length - 1 
    : currentTestimonial.value - 1
}

const goToTestimonial = (index) => {
  currentTestimonial.value = index
}
</script>

<template>
  <section id="testimonials" class="section-padding">
    <div class="container">
      <!-- Título de la sección -->
      <div class="row">
        <div class="col-lg-8 mx-auto text-center mb-5">
          <span class="badge bg-danger mb-3 px-3 py-2">
            <i class="fas fa-heart me-1"></i>
            Lo que dicen nuestros estudiantes
          </span>
          <h2 class="display-5 fw-bold mb-4">
            Más de <span class="text-danger">5,000 emprendedores</span> 
            ya transformaron sus negocios
          </h2>
          <p class="lead text-muted">
            Resultados reales de personas reales que aplicaron las estrategias del eBook
          </p>
        </div>
      </div>

      <!-- Testimonial principal (carousel) -->
      <div class="row mb-5">
        <div class="col-lg-10 mx-auto">
          <div class="testimonial-carousel">
            <div class="testimonial-main custom-shadow-hover p-5 rounded-3 bg-white">
              <div class="testimonial-content text-center">
                <!-- Avatar y info -->
                <div class="testimonial-header mb-4">
                  <div class="avatar-container mb-3">
                    <div class="avatar">
                      <i :class="testimonials[currentTestimonial].avatar + ' fa-3x text-danger'"></i>
                    </div>
                  </div>
                  
                  <div class="customer-info">
                    <h4 class="fw-bold mb-1">{{ testimonials[currentTestimonial].name }}</h4>
                    <p class="text-muted mb-2">
                      {{ testimonials[currentTestimonial].role }} • 
                      {{ testimonials[currentTestimonial].company }}
                    </p>
                    
                    <!-- Rating -->
                    <div class="rating mb-3">
                      <i 
                        v-for="star in testimonials[currentTestimonial].rating" 
                        :key="star"
                        class="fas fa-star text-warning"
                      ></i>
                    </div>
                  </div>
                </div>

                <!-- Testimonio -->
                <blockquote class="testimonial-text mb-4">
                  <p class="lead fst-italic">
                    "{{ testimonials[currentTestimonial].text }}"
                  </p>
                </blockquote>

                <!-- Resultados destacados -->
                <div class="results-highlight">
                  <div class="row justify-content-center">
                    <div class="col-md-6">
                      <div class="result-item">
                        <div class="result-number text-danger fw-bold fs-4">
                          {{ testimonials[currentTestimonial].result }}
                        </div>
                        <div class="result-label small">
                          En {{ testimonials[currentTestimonial].timeframe }}
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>

              <!-- Controles de navegación -->
              <div class="carousel-controls d-flex justify-content-between align-items-center mt-4">
                <button 
                  @click="prevTestimonial"
                  class="btn btn-outline-danger btn-sm"
                >
                  <i class="fas fa-chevron-left"></i>
                </button>

                <!-- Indicadores -->
                <div class="carousel-indicators">
                  <button
                    v-for="(testimonial, index) in testimonials"
                    :key="testimonial.id"
                    @click="goToTestimonial(index)"
                    :class="['indicator', { active: index === currentTestimonial }]"
                  ></button>
                </div>

                <button 
                  @click="nextTestimonial"
                  class="btn btn-outline-danger btn-sm"
                >
                  <i class="fas fa-chevron-right"></i>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Grid de testimonios secundarios -->
      <div class="row">
        <div class="col-12">
          <h4 class="text-center fw-bold mb-4">Más historias de éxito</h4>
          <div class="row g-4">
            <div 
              v-for="(testimonial, index) in testimonials.slice(0, 3)" 
              :key="testimonial.id"
              class="col-lg-4 col-md-6"
            >
              <div class="testimonial-card h-100 p-4 rounded-3 custom-shadow-hover">
                <div class="card-header d-flex align-items-center mb-3">
                  <div class="mini-avatar me-3">
                    <i :class="testimonial.avatar + ' fa-2x text-danger'"></i>
                  </div>
                  <div>
                    <h6 class="fw-bold mb-0">{{ testimonial.name }}</h6>
                    <small class="text-muted">{{ testimonial.role }}</small>
                  </div>
                </div>

                <div class="rating mb-2">
                  <i 
                    v-for="star in testimonial.rating" 
                    :key="star"
                    class="fas fa-star text-warning small"
                  ></i>
                </div>

                <p class="testimonial-excerpt text-muted mb-3">
                  {{ testimonial.text.substring(0, 120) }}...
                </p>

                <div class="mini-result">
                  <span class="badge bg-danger">{{ testimonial.result }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Estadísticas de satisfacción -->
      <div class="row mt-5">
        <div class="col-lg-10 mx-auto">
          <div class="satisfaction-stats p-4 rounded-3 bg-light text-center">
            <div class="row">
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-icon mb-2">
                    <i class="fas fa-users text-danger fa-2x"></i>
                  </div>
                  <div class="stat-number fw-bold text-danger fs-3">5,000+</div>
                  <div class="stat-label text-muted small">Estudiantes</div>
                </div>
              </div>
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-icon mb-2">
                    <i class="fas fa-star text-danger fa-2x"></i>
                  </div>
                  <div class="stat-number fw-bold text-danger fs-3">4.9★</div>
                  <div class="stat-label text-muted small">Calificación promedio</div>
                </div>
              </div>
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-icon mb-2">
                    <i class="fas fa-thumbs-up text-danger fa-2x"></i>
                  </div>
                  <div class="stat-number fw-bold text-danger fs-3">98%</div>
                  <div class="stat-label text-muted small">Recomendarían</div>
                </div>
              </div>
              <div class="col-md-3 col-6 mb-3">
                <div class="stat-item">
                  <div class="stat-icon mb-2">
                    <i class="fas fa-chart-line text-danger fa-2x"></i>
                  </div>
                  <div class="stat-number fw-bold text-danger fs-3">250%</div>
                  <div class="stat-label text-muted small">Aumento promedio</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Call to action después de testimonios -->
      <div class="row mt-5">
        <div class="col-lg-8 mx-auto text-center">
          <div class="cta-after-testimonials p-4 rounded-3">
            <h3 class="fw-bold mb-3">¿Listo para obtener resultados similares?</h3>
            <p class="mb-4">
              Únete a miles de emprendedores que ya están transformando sus negocios
            </p>
            <a 
              href="#pricing" 
              class="btn btn-custom-primary btn-lg"
            >
              <i class="fas fa-rocket me-2"></i>
              Quiero obtener el eBook ahora
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonial-carousel {
  position: relative;
}

.testimonial-main {
  border: 1px solid #e9ecef;
  transition: all 0.3s ease;
  min-height: 400px;
}

.avatar-container {
  display: flex;
  justify-content: center;
}

.avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.testimonial-text {
  position: relative;
  padding: 0 2rem;
}

.testimonial-text::before {
  content: '"';
  position: absolute;
  top: -20px;
  left: 0;
  font-size: 4rem;
  color: var(--primary-color);
  opacity: 0.3;
  font-family: serif;
}

.results-highlight {
  background: black;
  color: white;
  padding: 1.5rem;
  border-radius: 10px;
  margin-top: 1rem;
}

.result-item {
  text-align: center;
}

.carousel-controls {
  border-top: 1px solid #e9ecef;
  padding-top: 1rem;
}

.carousel-indicators {
  display: flex;
  gap: 0.5rem;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: none;
  background: #dee2e6;
  transition: all 0.3s ease;
}

.indicator.active {
  background: var(--primary-color);
  transform: scale(1.2);
}

.testimonial-card {
  background: white;
  border: 1px solid #e9ecef;
  transition: all 0.3s ease;
}

.testimonial-card:hover {
  border-color: var(--primary-color);
  transform: translateY(-5px);
}

.mini-avatar {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #f8f9fa;
  display: flex;
  align-items: center;
  justify-content: center;
}

.satisfaction-stats {
  border: 1px solid #e9ecef;
}

.stat-item {
  padding: 1rem;
}

.cta-after-testimonials {
  background: rgb(0, 0, 0);
  color: white;
}

/* Animaciones */
.testimonial-main {
  animation: fadeIn 0.5s ease-in;
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

.testimonial-card {
  animation: slideInUp 0.6s ease-out;
}

.testimonial-card:nth-child(1) { animation-delay: 0.1s; }
.testimonial-card:nth-child(2) { animation-delay: 0.2s; }
.testimonial-card:nth-child(3) { animation-delay: 0.3s; }

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
@media (max-width: 768px) {
  .testimonial-text {
    padding: 0 1rem;
  }
  
  .testimonial-text::before {
    font-size: 3rem;
    top: -15px;
  }
  
  .carousel-controls {
    flex-direction: column;
    gap: 1rem;
  }
  
  .stat-item {
    margin-bottom: 1rem;
  }
  
  .avatar {
    width: 60px;
    height: 60px;
  }
  
  .mini-avatar {
    width: 40px;
    height: 40px;
  }
}

@media (max-width: 575px) {
  .testimonial-main {
    padding: 2rem !important;
    min-height: auto;
  }
  
  .results-highlight {
    margin-top: 1rem;
    padding: 1rem;
  }
  
  .satisfaction-stats .row {
    text-align: center;
  }
}
</style>
