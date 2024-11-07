<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const monitor = ref(window.innerWidth)
const isMobile = ref(false)
const isOpen = ref(false)

onMounted(() => {
    monitor.value = window.innerWidth
    addEventListener('resize', () => {
        monitor.value = window.innerWidth
        if (monitor.value <= 768) {
            isMobile.value = true
        } else {
            isMobile.value = false
        }
    })
})

if (monitor.value <= 768) {
            isMobile.value = true
        } else {
            isMobile.value = false
        }

onUnmounted(() => {
    removeEventListener('resize', () => {
        monitor.value = window.innerWidth
    })
})

</script>
<template>
    <div class="navbar">
        <div class="menu-left" v-if="!isMobile">
            <button>Biografia</button>
            <button>Estilo</button>
        </div>

        <div class="titulo_site">
            {{ monitor }}
            <img src="../assets/silverspinningtoy.svg" alt="Pião" />
            <h1>Christopher <br> Nolan</h1>
        </div>
     
        <div class="menu-right" v-if="!isMobile">
            <button>Filmografia</button>
            <button>Início</button>
        </div>
        <div v-if="isMobile">
            <button @click="isOpen = !isOpen" class="hamburguer">☰</button>
            <div class="dropdown" v-if="isOpen">
                <div class="itens">
                    <button>Biografia</button>
                    <button>Estilo</button>
                    <button>Filmografia</button>
                    <button>Início</button>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
@import '../style.css';

.navbar{
    background-color: #1C1C1C;
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
}

h1{
    color: #D4E8F7;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.25rem;
    font-style: normal;
    font-weight: 400;
    line-height: 1.6;
}

.titulo_site{
    display: flex;
    align-items: center;
    width: 16.31rem;
    height: 5.63rem;

}

.menu-left, .menu-right{
    display: flex;
    gap: 5rem;
    padding: 48px;
}

button{
    background-color: #1C1C1C;
    color: white;
    border: none;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    transition: 0.3s ease-in-out;
    font-family: Arial, Helvetica, sans-serif;
    font-style: normal;
}


button:hover{
    background-color: #D4E8F7;
    color: #1C1C1C;
}

.hamburguer{
    display: flex;
    padding: 0.5rem o.6rem;
    margin: 0 2rem;

}

.itens{
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: 1rem;
    background-color: #1C1C1C;
    color: white;
    position: absolute;
    top: 5rem;
    right: 0;
    width: 100%;
}
</style>
