<!-- .\components\SobreMi.vue -->
<template>
    <section id="sobremi" class="sobremi">
        <div class="contenido-seccion">

            <h2>Sobre Mí</h2>
            <p><span>¡Hola!👋 soy Leonardo Corales</span>, estudiante de la Tecnicatura Universitaria en Programación en <span><a href="https://www.frgp.utn.edu.ar" class="link">(UTN - FRGP)</a></span> y desarrollador web Front-End en formación. Me apasiona crear interfaces intuitivas, visualmente atractivas y adaptadas a las necesidades del usuario. Trabajo con tecnologías como HTML, CSS, JavaScript y frameworks modernos como Vue y Tailwind. Este portafolio refleja mi evolución como desarrollador y mi interés por seguir creciendo en el mundo del desarrollo web. ¡Te invito a explorar mis proyectos!</p>

            <div class="fila">
                <!-- datos personales -->
                <div class="col">
                    <h3>Datos Personales</h3>
                    <ul>
                        <li>
                            <strong>Fecha de Nacimiento</strong>
                            24/02/2000
                        </li>
                        <li>
                            <strong>Teléfono</strong>
                            +54 9 11 4086 0438
                        </li>
                        <li>
                            <strong>Email</strong>
                            leo24corales@gmail.com
                        </li>
                        <li>
                            <strong>Dirección</strong>
                            Jose C. Paz, Buenos Aires
                        </li>
                    </ul>
                </div>

                <!-- Metodos de contacto -->
                <div class="col">
                    <h3>Contactame</h3>
                    <div class="contenedor-contacto">
                        <a href="https://github.com/leo-em" target="_blank" rel="noopener noreferrer" class="contacto">
                            <i class="fa-brands fa-github"></i>
                            <span>GitHub</span>
                        </a>
                        <a href="https://linkedin.com/in/leonardo-corales/" target="_blank" rel="noopener noreferrer" class="contacto">
                            <i class="fa-brands fa-linkedin linkedin-icon"></i>
                            <span>Linkedin</span>
                        </a>
                        <a href="mailto:leo24corales@gmail.com" target="_blank" rel="noopener noreferrer" class="contacto">
                            <i class="fa-solid fa-envelope email-icon"></i>
                            <span>Email</span>
                        </a>
                        <a href="https://api.whatsapp.com/send/?phone=5491140860438" target="_blank" rel="noopener noreferrer" class="contacto">
                            <i class="fa-brands fa-whatsapp whatsapp-icon"></i>
                            <span>Mensaje</span>
                        </a>
                    </div>
                </div>
            </div>
            <a href="cv/CV.pdf" target="_blank" rel="noopener noreferrer" class="boton-cv">
                Descargar CV <i class="fa-solid fa-download"></i>
                <span class="overlay"></span>
            </a>
        </div>
    </section>
</template>

<style scoped>
    .boton-cv {
    cursor: pointer;
    background-color: transparent;
    border: 2px solid #fff;
    width: fit-content;
    display: block;
    margin: 20px auto;
    padding: 10px 22px;
    font-size: 16px;
    color: #fff;
    position: relative;
    z-index: 10;
    text-decoration: none;
    }

    .boton-cv .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 0;
    height: 100%;
    background-color: #1CB698;
    z-index: -1;
    transition: 1s;
    }

    .boton-cv:hover .overlay {
    width: 100%;
    }

    .contenedor-contacto .contacto {
        text-decoration: none;
        color: inherit;
    }
</style>

<script setup>  
    // No es necesario para este componente
</script>