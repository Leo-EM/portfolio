<!-- .\components\Portfolio.vue -->
<template>
    <section id="portfolio" class="portfolio">
        <div class="contenido-seccion">
            <h2>PORTFOLIO</h2>
            <div class="galeria">
                <ProjectCard
                    v-for="project in projects"
                    :key="project.id"
                    :title="project.title"
                    :description="project.description"
                    :link="project.link"
                    :techs="project.techs"
                    :image="project.image"
                />
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
    import ProjectCard from '../components/ProjectCard.vue'
  
    interface Project {
        id: number;
        image: string;
        title: string;
        description: string;
        link: string;
        techs: string[];
    }
  
    const projects: Project[] = [
        {
        id: 1,
        image: '/cesar.png',
        title: 'Cifrador César',
        description: 'Una landing moderna para un caracteristico projecto de cifrado de texto.',
        link: 'https://leo-em.github.io/Cifrador-Cesar/',
        techs: ['HTML', 'CSS', 'JavaScript']
        },
        {
        id: 2,
        image: '',
        title: 'Dashboard Administrativo',
        description: 'Panel para gestionar productos, usuarios y reportes.',
        link: 'https://tusitio.com/proyecto2',
        techs: ['Vue', 'Pinia', 'Chart.js'],
        }
    ]
</script>
  