<script setup>
import { ref } from 'vue'

const achievements = ref([
    {
        icon: 'fas fa-trophy',
        text: '+10 años de experiencia en marketing digital'
    },
    {
        icon: 'fas fa-users',
        text: 'Ha entrenado a más de 50,000 emprendedores'
    },
    {
        icon: 'fas fa-chart-line',
        text: 'Generado +$5M en ventas para sus clientes'
    },
    {
        icon: 'fas fa-award',
        text: 'Reconocido como Top Marketing Influencer 2023'
    }
])

const credentials = ref([
    'Certificación Google Ads',
    'Facebook Marketing Partner',
    'Mentor en Y Combinator',
    'Speaker en 20+ conferencias internacionales'
])
</script>

<template>
    <section id="author" class="section-padding">
        <div class="container">
            <div class="row align-items-center">
                <!-- Foto y información básica del autor -->
                <div class="col-lg-5 text-center mb-5 mb-lg-0">
                    <div class="author-image-container">
                        <!-- Placeholder para foto del autor -->
                        <div class="author-image custom-shadow">
                            <div class="image-placeholder">
                                <i class="fas fa-user fa-5x"></i>
                            </div>
                        </div>

                        <!-- Badges de credibilidad -->
                        <div class="author-badges mt-4">
                            <span class="badge bg-danger me-2 mb-2">
                                <i class="fas fa-graduation-cap me-1"></i>
                                MBA Marketing
                            </span>
                            <span class="badge bg-dark me-2 mb-2">
                                <i class="fas fa-certificate me-1"></i>
                                Google Partner
                            </span>
                            <span class="badge bg-danger mb-2">
                                <i class="fas fa-medal me-1"></i>
                                Top Seller
                            </span>
                        </div>

                        <!-- Redes sociales -->
                        <div class="social-links mt-4">
                            <a href="#" class="social-link me-3">
                                <i class="fab fa-linkedin-in"></i>
                            </a>
                            <a href="#" class="social-link me-3">
                                <i class="fab fa-twitter"></i>
                            </a>
                            <a href="#" class="social-link me-3">
                                <i class="fab fa-instagram"></i>
                            </a>
                            <a href="#" class="social-link">
                                <i class="fab fa-youtube"></i>
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Contenido sobre el autor -->
                <div class="col-lg-7">
                    <div class="author-content">
                        <span class="badge bg-danger text-white mb-3 px-3 py-2">
                            <i class="fas fa-star me-1"></i>
                            Sobre el Autor
                        </span>

                        <h2 class="display-6 fw-bold mb-4">
                            Conoce a <span class="text-danger">Juan Pérez</span>
                        </h2>

                        <p class="lead mb-4">
                            Experto en Marketing Digital con más de una década transformando
                            negocios y ayudando a emprendedores a escalar sus ventas online.
                        </p>

                        <p class="mb-4 text-muted">
                            Juan comenzó su carrera trabajando con startups en Silicon Valley,
                            donde aprendió las estrategias más avanzadas de growth hacking y
                            marketing digital. Desde entonces, ha fundado 3 empresas exitosas
                            y ha asesorado a cientos de emprendedores a alcanzar sus metas.
                        </p>

                        <!-- Logros destacados -->
                        <div class="achievements mb-5">
                            <h4 class="fw-bold mb-3 text-danger">
                                <i class="fas fa-rocket me-2"></i>
                                Logros Destacados
                            </h4>
                            <div class="row g-3">
                                <div v-for="(achievement, index) in achievements" :key="index" class="col-md-6">
                                    <div class="achievement-item">
                                        <i :class="achievement.icon + ' text-danger me-2'"></i>
                                        <span class="fw-semibold">{{ achievement.text }}</span>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Credenciales -->
                        <div class="credentials mb-4">
                            <h5 class="fw-bold mb-3">Certificaciones y Reconocimientos:</h5>
                            <div class="credentials-list">
                                <div v-for="(credential, index) in credentials" :key="index"
                                    class="credential-item mb-2">
                                    <i class="fas fa-check-circle text-danger me-2"></i>
                                    <span>{{ credential }}</span>
                                </div>
                            </div>
                        </div>

                        <!-- Quote personal -->
                        <div class="author-quote p-4 rounded-3 bg-light border-start border-danger border-4">
                            <blockquote class="mb-3">
                                <p class="fst-italic text-muted">
                                    "Mi misión es democratizar el conocimiento del marketing digital.
                                    Creo firmemente que cualquier persona con las estrategias correctas
                                    puede construir un negocio próspero online."
                                </p>
                            </blockquote>
                            <div class="quote-author">
                                <strong class="text-danger">— Juan Pérez</strong>
                                <small class="text-muted d-block">Fundador & CEO, Digital Success Academy</small>
                            </div>
                        </div>

                        <!-- Estadísticas del autor -->
                        <div class="author-stats mt-4">
                            <div class="row text-center">
                                <div class="col-4">
                                    <div class="stat-value text-danger fw-bold fs-4">50K+</div>
                                    <div class="stat-label text-muted small">Estudiantes</div>
                                </div>
                                <div class="col-4">
                                    <div class="stat-value text-danger fw-bold fs-4">15+</div>
                                    <div class="stat-label text-muted small">Años Exp.</div>
                                </div>
                                <div class="col-4">
                                    <div class="stat-value text-danger fw-bold fs-4">98%</div>
                                    <div class="stat-label text-muted small">Satisfacción</div>
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
.author-image-container {
    position: relative;
}

.author-image {
    width: 250px;
    height: 250px;
    border-radius: 50%;
    margin: 0 auto;
    background: #f8f9fa;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 5px solid white;
    position: relative;
    overflow: hidden;
}

.image-placeholder {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: var(--bg-dark);
    color: white;
}

.author-badges .badge {
    font-size: 0.75rem;
    padding: 0.5rem 1rem;
}

.social-links {
    display: flex;
    justify-content: center;
    gap: 1rem;
}

.social-link {
    width: 45px;
    height: 45px;
    border-radius: 50%;
    background: var(--primary-color);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    transition: all 0.3s ease;
    font-size: 1.2rem;
}

.social-link:hover {
    transform: translateY(-3px);
    box-shadow: 0 5px 15px rgba(220, 38, 38, 0.4);
    color: white;
}

.achievement-item {
    display: flex;
    align-items: center;
    padding: 0.5rem 0;
}

.achievement-item i {
    font-size: 1.1rem;
    width: 20px;
}

.credential-item {
    display: flex;
    align-items: center;
}

.author-quote {
    position: relative;
}

.author-quote::before {
    content: '"';
    position: absolute;
    top: -10px;
    left: 15px;
    font-size: 4rem;
    color: var(--primary-color);
    opacity: 0.3;
    font-family: serif;
}

.author-stats {
    background: white;
    border-radius: 10px;
    padding: 1.5rem;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.press-section {
    padding: 2rem 0;
    background: #f8f9fa;
    border-radius: 15px;
}

.press-item .badge {
    font-size: 0.9rem;
    font-weight: 500;
    border: 1px solid #dee2e6;
}

/* Animaciones */
.author-content {
    animation: fadeInRight 0.8s ease-out;
}

.author-image-container {
    animation: fadeInLeft 0.8s ease-out;
}

@keyframes fadeInLeft {
    from {
        opacity: 0;
        transform: translateX(-30px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}

@keyframes fadeInRight {
    from {
        opacity: 0;
        transform: translateX(30px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}

/* Responsive */
@media (max-width: 991px) {
    .author-image {
        width: 200px;
        height: 200px;
    }

    .achievement-item {
        font-size: 0.9rem;
    }

    .social-links {
        margin-top: 2rem;
    }
}

@media (max-width: 575px) {
    .author-image {
        width: 180px;
        height: 180px;
    }

    .press-logos {
        flex-direction: column;
        gap: 1rem;
    }

    .author-stats .row>div {
        margin-bottom: 1rem;
    }
}
</style>
