<!-- .\components\Contacto.vue -->
<template>
    <section id="contacto" class="contacto">
        <div class="contenido-seccion">
            <h2>CONTACTO</h2>
            <p class="mensaje"> Puedes comunicarte conmigo de forma directa ante cualquier propuesta o consulta profesional.</p>
            
            <div class="fila">
                <!-- Formulario -->
                <form @submit.prevent="sendEmail" ref="formRef" class="space-y-4">
                    <div class="col">
                        <div>
                            <input v-model="form.name" type="text" name="name" required placeholder="Tú Nombre">
                            <p v-if="errors.name" class="error">{{ errors.name }}</p>
                        </div>
                        
                        <div>
                            <input v-model="form.email" type="email" name="email" required placeholder="Dirección de correo">
                            <p v-if="errors.email" class="error">{{ errors.email }}</p>
                        </div>
                        
                        <div>
                            <textarea v-model="form.message" name="message" required cols="120" rows="10" placeholder="Mensaje"></textarea>
                            <p v-if="errors.message" class="error">{{ errors.message }}</p>
                        </div>

                        <button type="submit">
                            Enviar Mensaje <i class="fa-solid fa-paper-plane"></i>
                            <span class="overlay"></span>
                        </button>

                        <p v-if="successMessage" class="success">{{ successMessage }}</p>
                        <p v-if="submitError" class="error">{{ submitError }}</p>
                    </div>
                </form>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
    import { ref } from 'vue'
    import emailjs from '@emailjs/browser'

    const formRef = ref<HTMLFormElement | null>(null)

    const form = ref({
    name: '',
    email: '',
    message: ''
    })

    const errors = ref({
    name: '',
    email: '',
    message: ''
    })

    const successMessage = ref('')
    const submitError = ref('')

    const validateEmail = (email: string) => {
    const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
    return regex.test(email)
    }

    const sendEmail = () => {
    // Limpiar errores previos
    errors.value = { name: '', email: '', message: '' }
    submitError.value = ''
    successMessage.value = ''

    // Validaciones
    let valid = true

    if (!form.value.name.trim()) {
        errors.value.name = 'El nombre es obligatorio.'
        valid = false
    }

    if (!form.value.email.trim()) {
        errors.value.email = 'El correo es obligatorio.'
        valid = false
    } else if (!validateEmail(form.value.email)) {
        errors.value.email = 'El correo no es válido.'
        valid = false
    }

    if (!form.value.message.trim()) {
        errors.value.message = 'El mensaje es obligatorio.'
        valid = false
    }

    if (!valid) return

    if (!formRef.value) return

    emailjs
        .sendForm('service_7gprqqo', 'template_3mhtoxi', formRef.value, 'DsWuZzd-JZQdRqCFD')
        .then(() => {
        successMessage.value = '¡Mensaje enviado con éxito!'
        form.value = { name: '', email: '', message: '' }
        })
        .catch((error) => {
        console.error('Error al enviar:', error)
        submitError.value = 'Ocurrió un error al enviar el mensaje. Intenta de nuevo.'
        })
    }
</script>