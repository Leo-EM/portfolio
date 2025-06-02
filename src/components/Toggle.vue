<template>
    <button class="modo-toggle" @click="toggle">
        <i :class="isDarkMode ? 'fa-solid fa-sun' : 'fa-solid fa-moon'"></i>
    </button>
</template>
  
<script setup>
    import { ref, onMounted } from 'vue'

const isDarkMode = ref(false)

const toggle = () => {
    isDarkMode.value = !isDarkMode.value
        updateBodyClass()
        localStorage.setItem('dark-mode', isDarkMode.value ? '1' : '0')
    }

    const updateBodyClass = () => {
        if (isDarkMode.value) {
            document.body.classList.add('dark-mode')
        } else {
            document.body.classList.remove('dark-mode')
        }
    }

    // Restaurar preferencia del usuario al cargar
    onMounted(() => {
        isDarkMode.value = localStorage.getItem('dark-mode') === '1'
        updateBodyClass()
    })
</script>
  
<style scoped>
    .modo-toggle {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background-color: #1CB698;
        color: white;
        border: none;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        cursor: pointer;
        z-index: 1000;
        font-size: 18px;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: background-color 0.3s;
    }
  
    .modo-toggle:hover {
        background-color: #159980;
    }
</style>
  