<!-- src/components/ProjectCard.vue -->
<template>
  <div class="proyecto">
    <a
      :href="link"
      target="_blank"
      class=""
    >
    <img :src="image" alt="Imagen del proyecto" class="" />
    <h2 class="">{{ title }}</h2>
    <p class="">{{ description }}</p>
    <ul class="overlay">
      <li
        v-for="(tech, index) in techs"
        :key="index"
        class=""
      >
        {{ tech }}
      </li>
    </ul>
    
    </a>  
  </div>
</template>
  
<script setup lang="ts">
  defineProps<{
    title: string
    description: string
    link: string
    techs: string[]
    image: string
  }>()
</script>
  