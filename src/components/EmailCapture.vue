<script setup>
import { ref } from 'vue'

const email = ref('')
const isSubmitting = ref(false)
const isSubmitted = ref(false)
const errorMessage = ref('')

const submitEmail = async () => {
    if (!email.value) {
        errorMessage.value = 'Por favor ingresa tu email'
        return
    }

    if (!isValidEmail(email.value)) {
        errorMessage.value = 'Por favor ingresa un email válido'
        return
    }

    isSubmitting.value = true
    errorMessage.value = ''

    try {
        // Aquí irías la integración con tu servicio de email
        // Por ejemplo: Formspree, Mailchimp, ConvertKit, etc.

        // Simulación de envío
        await new Promise(resolve => setTimeout(resolve, 1500))

        // Para integrar con Formspree:
        // const response = await fetch('https://formspree.io/f/YOUR_FORM_ID', {
        //   method: 'POST',
        //   headers: { 'Content-Type': 'application/json' },
        //   body: JSON.stringify({ email: email.value })
        // })

        isSubmitted.value = true
        email.value = ''
    } catch (error) {
        errorMessage.value = 'Error al suscribirte. Inténtalo de nuevo.'
    } finally {
        isSubmitting.value = false
    }
}

const isValidEmail = (email) => {
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
    return emailRegex.test(email)
}

const resetForm = () => {
    isSubmitted.value = false
    errorMessage.value = ''
}
</script>

<template>
    <section id="email-capture" class="section-padding section-light">
        <div class="container">
            <div class="row">
                <div class="col-lg-8 mx-auto">
                    <div class="email-capture-card custom-shadow p-5 rounded-3">
                        <!-- Estado normal del formulario -->
                        <div v-if="!isSubmitted" class="form-content text-center">
                            <div class="icon-container mb-4">
                                <i class="fas fa-download fa-3x text-white"></i>
                            </div>

                            <h2 class="fw-bold mb-3">
                                ¡Descarga el <span class="text-danger">Primer Capítulo</span> GRATIS!
                            </h2>

                            <p class="lead text-muted mb-4">
                                Recibe los primeros 20 páginas del eBook + una hoja de ruta exclusiva
                                para implementar tu primera campaña de marketing digital en 7 días.
                            </p>

                            <!-- Beneficios de suscribirse -->
                            <div class="benefits-list mb-4">
                                <div class="row text-start">
                                    <div class="col-md-6">
                                        <div class="benefit-item mb-2">
                                            <i class="fas fa-check-circle text-success me-2"></i>
                                            <span>Primer capítulo completo (20 páginas)</span>
                                        </div>
                                        <div class="benefit-item mb-2">
                                            <i class="fas fa-check-circle text-success me-2"></i>
                                            <span>Hoja de ruta de 7 días</span>
                                        </div>
                                    </div>
                                    <div class="col-md-6">
                                        <div class="benefit-item mb-2">
                                            <i class="fas fa-check-circle text-success me-2"></i>
                                            <span>Tips exclusivos semanales</span>
                                        </div>
                                        <div class="benefit-item mb-2">
                                            <i class="fas fa-check-circle text-success me-2"></i>
                                            <span>Acceso a contenido premium</span>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <!-- Formulario -->
                            <form @submit.prevent="submitEmail" class="email-form">
                                <div class="input-group input-group-lg mb-3">
                                    <span class="input-group-text">
                                        <i class="fas fa-envelope text-muted"></i>
                                    </span>
                                    <input v-model="email" type="email" class="form-control"
                                        placeholder="Tu mejor email aquí..." :disabled="isSubmitting">
                                    <button type="submit" class="btn btn-custom-primary" :disabled="isSubmitting">
                                        <span v-if="!isSubmitting">
                                            <i class="fas fa-download me-2"></i>
                                            Descargar Gratis
                                        </span>
                                        <span v-else>
                                            <i class="fas fa-spinner fa-spin me-2"></i>
                                            Enviando...
                                        </span>
                                    </button>
                                </div>

                                <!-- Mensaje de error -->
                                <div v-if="errorMessage" class="alert alert-danger mt-3">
                                    <i class="fas fa-exclamation-triangle me-2"></i>
                                    {{ errorMessage }}
                                </div>
                            </form>

                            <!-- Garantía de privacidad -->
                            <div class="privacy-notice mt-4">
                                <small class="text-muted">
                                    <i class="fas fa-shield-alt text-danger me-1"></i>
                                    No spam, solo contenido valioso. Puedes darte de baja en cualquier momento.
                                </small>
                            </div>

                            <!-- Social proof -->
                            <div class="social-proof mt-4">
                                <div class="d-flex justify-content-center align-items-center flex-wrap">
                                    <small class="text-muted me-3">Ya se han suscrito:</small>
                                    <div class="subscriber-count">
                                        <span class="badge bg-danger px-3 py-2">
                                            <i class="fas fa-users me-1"></i>
                                            12,547 emprendedores
                                        </span>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Estado de éxito -->
                        <div v-else class="success-content text-center">
                            <div class="success-icon mb-4">
                                <i class="fas fa-check-circle fa-4x text-danger"></i>
                            </div>

                            <h3 class="fw-bold text-danger mb-3">
                                ¡Perfecto! Revisa tu email
                            </h3>

                            <p class="lead text-muted mb-4">
                                Te hemos enviado el primer capítulo y la hoja de ruta a tu email.
                                Si no lo ves en unos minutos, revisa tu carpeta de spam.
                            </p>

                            <div class="next-steps mb-4">
                                <h5 class="fw-bold mb-3">Mientras tanto:</h5>
                                <div class="row">
                                    <div class="col-md-6 mb-3">
                                        <div class="next-step-item p-3 rounded bg-light">
                                            <i class="fas fa-heart text-danger mb-2"></i>
                                            <div class="small">
                                                <strong>Síguenos en redes</strong><br>
                                                Para más tips diarios
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-md-6 mb-3">
                                        <div class="next-step-item p-3 rounded bg-light">
                                            <i class="fas fa-shopping-cart text-danger mb-2"></i>
                                            <div class="small">
                                                <strong>¿Te gustó? Adquiere el libro completo</strong><br>
                                                Con 50% de descuento especial
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <button @click="resetForm" class="btn btn-outline-danger me-3">
                                <i class="fas fa-arrow-left me-2"></i>
                                Volver
                            </button>

                            <a href="#pricing" class="btn btn-custom-primary">
                                <i class="fas fa-shopping-cart me-2"></i>
                                Ver Oferta Completa
                            </a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Testimonios rápidos de la newsletter -->
            
        </div>
    </section>
</template>

<style scoped>
.email-capture-card {
    background: white;
    border: 1px solid #e9ecef;
    position: relative;
    overflow: hidden;
}

.email-capture-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 5px;
    background: var(--primary-color);
}

.icon-container {
    width: 80px;
    height: 80px;
    background: var(--bg-dark);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto;
    color: white;
}

.benefits-list {
    background: #f8f9fa;
    border-radius: 10px;
    padding: 1.5rem;
}

.benefit-item {
    display: flex;
    align-items: center;
    font-weight: 500;
}

.email-form .input-group {
    max-width: 600px;
    margin: 0 auto;
}

.email-form .form-control {
    border: 2px solid #e9ecef;
    border-radius: 50px 0 0 50px;
    padding: 15px 20px;
    
}

.email-form .form-control:focus {
    border-color: var(--primary-color);
    box-shadow: 0 0 0 0.2rem rgba(220, 38, 38, 0.25);
}

.email-form .input-group-text {
    background: #f8f9fa;
    border: 2px solid #e9ecef;
    border-right: none;
    border-radius: 50px 0 0 50px;
}

.email-form .btn {
    border-radius: 0 50px 50px 0;
    padding: 15px 25px;
    border: 2px solid var(--primary-color);
}

.privacy-notice {
    padding: 1rem;
    background: #f8f9fa;
    border-radius: 10px;
}

.social-proof {
    border-top: 1px solid #e9ecef;
    padding-top: 1.5rem;
}

.subscriber-count .badge {
    font-size: 0.9rem;
    animation: pulse 2s infinite;
}

@keyframes pulse {
    0% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.05);
    }

    100% {
        transform: scale(1);
    }
}

.success-icon {
    animation: bounceIn 0.8s ease-out;
}

@keyframes bounceIn {
    0% {
        transform: scale(0.3);
        opacity: 0;
    }

    50% {
        transform: scale(1.05);
    }

    70% {
        transform: scale(0.9);
    }

    100% {
        transform: scale(1);
        opacity: 1;
    }
}

.next-step-item {
    border: 1px solid #e9ecef;
    transition: all 0.3s ease;
    height: 100%;
}

.next-step-item:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.newsletter-testimonials {
    background: white;
    border-radius: 15px;
    padding: 2rem;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.testimonial-mini {
    border-radius: 10px;
    border: 1px solid #e9ecef;
    transition: all 0.3s ease;
}

.testimonial-mini:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.stars {
    font-size: 0.9rem;
}

/* Responsive */
@media (max-width: 991px) {
    .email-capture-card {
        margin: 0 1rem;
    }
    
    h2 {
        font-size: 1.75rem;
    }
    
    .lead {
        font-size: 1.1rem;
    }
    
    .benefits-list {
        padding: 1.25rem;
    }
    
    .email-form .input-group {
        max-width: 100%;
    }
}

@media (max-width: 768px) {
    .email-capture-card {
        padding: 2.5rem !important;
        margin: 0 0.5rem;
    }
    
    h2 {
        font-size: 1.5rem;
        line-height: 1.3;
    }
    
    .lead {
        font-size: 1rem;
        margin-bottom: 2rem !important;
    }
    
    .icon-container {
        width: 70px;
        height: 70px;
        margin-bottom: 1.5rem !important;
    }
    
    .icon-container i {
        font-size: 2.25rem;
    }
    
    .benefits-list {
        padding: 1.5rem 1rem;
        margin-bottom: 2rem !important;
    }
    
    .benefits-list .row {
        text-align: center;
    }
    
    .benefit-item {
        justify-content: center;
        margin-bottom: 0.75rem !important;
        font-size: 0.95rem;
    }

    .email-form .input-group {
        flex-direction: column;
        gap: 0.75rem;
    }

    .email-form .form-control,
    .email-form .input-group-text,
    .email-form .btn {
        border-radius: 50px;
        border: 2px solid #e9ecef;
        margin-bottom: 0;
    }
    
    .email-form .form-control {
        padding: 1rem 1.25rem;
        font-size: 1rem;
        text-align: center;
        width: auto;
    }

    .email-form .input-group-text {
        justify-content: center;
        padding: 1rem;
        border-bottom: none;
        border-radius: 50px 50px 0 0;
    }
    
    .email-form .btn {
        padding: 1rem 1.5rem;
        font-size: 1rem;
        font-weight: 600;
        border-radius: 0 0 50px 50px;
        border-top: none;
    }
    
    .privacy-notice {
        margin-top: 2rem !important;
        padding: 1rem;
        font-size: 0.875rem;
    }

    .social-proof {
        flex-direction: column;
        gap: 1rem;
        margin-top: 2rem !important;
        text-align: center;
    }
    
    .subscriber-count .badge {
        font-size: 0.875rem;
        padding: 0.75rem 1.25rem;
    }
    
    /* Success state mobile */
    .success-content h3 {
        font-size: 1.5rem;
    }
    
    .success-content .lead {
        font-size: 0.95rem;
    }
    
    .next-steps h5 {
        font-size: 1.125rem;
    }
    
    .next-step-item {
        margin-bottom: 1rem;
        padding: 1rem !important;
    }
    
    .next-step-item .small {
        font-size: 0.875rem;
    }
}

@media (max-width: 575px) {
    .email-capture-card {
        padding: 2rem 1.5rem !important;
        margin: 0;
        border-radius: 1rem !important;
    }
    
    h2 {
        font-size: 1.375rem;
        line-height: 1.25;
        margin-bottom: 1rem !important;
    }
    
    .lead {
        font-size: 0.95rem;
        line-height: 1.5;
        margin-bottom: 1.5rem !important;
    }

    .icon-container {
        width: 60px;
        height: 60px;
        margin-bottom: 1rem !important;
    }

    .icon-container i {
        font-size: 2rem;
    }
    
    .benefits-list {
        padding: 1rem;
        margin-bottom: 1.5rem !important;
        border-radius: 0.75rem;
    }
    
    .benefit-item {
        font-size: 0.875rem;
        margin-bottom: 0.625rem !important;
        gap: 0.5rem;
    }
    
    .benefit-item i {
        font-size: 0.875rem;
    }
    
    .email-form .input-group {
        gap: 0.5rem;
    }
    
    .email-form .form-control {
        padding: 0.875rem 1rem;
        font-size: 0.95rem;
        width: auto;
    }
    
    .email-form .input-group-text {
        padding: 0.875rem;
    }
    
    .email-form .btn {
        padding: 0.875rem 1.25rem;
        font-size: 0.95rem;
    }
    
    .privacy-notice {
        padding: 0.875rem;
        margin-top: 1.5rem !important;
        font-size: 0.8rem;
        border-radius: 0.75rem;
    }
    
    .social-proof {
        margin-top: 1.5rem !important;
        padding-top: 1rem;
    }
    
    .social-proof small {
        font-size: 0.8rem;
        margin-bottom: 0.5rem;
        display: block;
    }
    
    .subscriber-count .badge {
        font-size: 0.8rem;
        padding: 0.625rem 1rem;
    }
    
    /* Success state mobile improvements */
    .success-content h3 {
        font-size: 1.25rem;
        margin-bottom: 1rem !important;
    }
    
    .success-content .lead {
        font-size: 0.875rem;
        margin-bottom: 1.5rem !important;
    }
    
    .success-icon {
        margin-bottom: 1rem !important;
    }
    
    .success-icon i {
        font-size: 3rem !important;
    }
    
    .next-steps {
        margin-bottom: 2rem !important;
    }
    
    .next-steps h5 {
        font-size: 1rem;
        margin-bottom: 1rem !important;
    }
    
    .next-step-item {
        padding: 0.875rem !important;
        margin-bottom: 0.75rem;
        text-align: center;
    }
    
    .next-step-item i {
        font-size: 1.25rem;
        margin-bottom: 0.5rem !important;
    }
    
    .next-step-item .small {
        font-size: 0.8rem;
    }
    
    .success-content .btn {
        width: 100%;
        margin-bottom: 0.75rem;
        padding: 0.875rem;
        font-size: 0.95rem;
    }
    
    .success-content .btn:last-child {
        margin-bottom: 0;
    }
    
    /* Alert messages */
    .alert {
        font-size: 0.875rem;
        padding: 0.75rem 1rem;
        border-radius: 0.75rem;
    }
}

@media (max-width: 380px) {
    .email-capture-card {
        padding: 1.5rem 1rem !important;
        border-radius: 0.75rem !important;
    }
    
    h2 {
        font-size: 1.25rem;
        line-height: 1.2;
    }
    
    .lead {
        font-size: 0.9rem;
    }
    
    .icon-container {
        width: 50px;
        height: 50px;
    }
    
    .icon-container i {
        font-size: 1.75rem;
    }
    
    .benefits-list {
        padding: 0.875rem;
    }
    
    .benefit-item {
        font-size: 0.8rem;
    }
    
    .email-form .form-control,
    .email-form .input-group-text,
    .email-form .btn {
        padding: 0.75rem 0.875rem;
        font-size: 0.9rem;
    }
    
    .privacy-notice,
    .social-proof small,
    .subscriber-count .badge {
        font-size: 0.75rem;
    }
    
    .subscriber-count .badge {
        padding: 0.5rem 0.875rem;
    }
    
    .success-content h3 {
        font-size: 1.125rem;
    }
    
    .success-content .lead {
        font-size: 0.825rem;
    }
    
    .next-step-item {
        padding: 0.75rem !important;
    }
    
    .next-step-item .small {
        font-size: 0.75rem;
    }
}
</style>
