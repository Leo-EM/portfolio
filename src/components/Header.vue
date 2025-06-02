<!-- .\components\Header.vue -->
<template>
    <div class="contenedor-header">
      <header>
        <div class="logo">
          <a href="#">＜╱＞</a>
        </div>
  
        <!-- Botón hamburguesa -->
        <div class="nav-responsive" @click="toggleMenu">
          <i class="fa-solid fa-bars"></i>
        </div>
  
        <!-- Menú -->
        <nav :class="menuVisible ? 'main-nav responsive' : 'main-nav'">
          <ul>
            <li><a href="#inicio" @click="closeMenu">INICIO</a></li>
            <li><a href="#sobremi" @click="closeMenu">SOBRE MI</a></li>
            <li><a href="#skills" @click="closeMenu">SKILLS</a></li>
            <li><a href="#portfolio" @click="closeMenu">PORTFOLIO</a></li>
            <li><a href="#contacto" @click="closeMenu">CONTACTO</a></li>
          </ul>
        </nav>
      </header>
    </div>
</template>
  
<script setup>
  import { ref } from 'vue'
  
  const menuVisible = ref(false)
  
  function toggleMenu() {
    menuVisible.value = !menuVisible.value
  }
  
  function closeMenu() {
    menuVisible.value = false
  }
</script>
  
<style>
    @media screen and (max-width: 980px) {
        .nav-responsive {
            display: block;
            background-color: #1CB698;
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            z-index: 101;
        }

        .main-nav {
            display: none;
        }

        .main-nav.responsive {
            display: block;
            position: absolute;
            top: 75px;
            right: 0;
            width: 180px;
            background-color: #252A2E;
            z-index: 100;
        }

        .main-nav.responsive ul {
            display: block;
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .main-nav.responsive ul li {
            border-bottom: 1px solid white;
            padding: 10px;
        }

        .main-nav.responsive ul li a {
            color: white;
            text-decoration: none;
        }
    }

    /* En pantallas grandes */
    @media screen and (min-width: 981px) {
        .nav-responsive {
            display: none;
        }

        .main-nav {
            display: flex;
        }

        .main-nav ul {
            display: flex;
            gap: 15px;
        }

        .main-nav ul li a {
            color: white;
            text-decoration: none;
        }

        .main-nav ul li a:hover {
            color: #1CB698;
        }
    }
</style>