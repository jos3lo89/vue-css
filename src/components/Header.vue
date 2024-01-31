<script setup>
import { ref } from 'vue';
const valorMenu = ref(false)
const abrirMenu = () => {
    valorMenu.value = !valorMenu.value
}

const datosUrl = [
    {
        nombre: "inicio",
        url: "/"
    },
    {
        nombre: "contacto",
        url: "/contact"
    },
]

</script>

<template>
    <header class="header">
        <div class="logo">
            <h1>joselo <span>33</span></h1>
        </div>
        <nav v-bind:class="[valorMenu ? 'navBar active' : 'navBar']">
            <a v-bind:href="dato.url" v-for="dato in datosUrl">{{ dato.nombre }}</a>
        </nav>
        <div class="btnBox">
            <i v-on:click="abrirMenu()" v-bind:class="[valorMenu ? 'bi bi-x' : 'bi bi-list']"></i>
        </div>
        
    </header>
</template>

<style scoped>
.header {
    background-color: #303030;
    display: flex;
    justify-content: space-around;
    align-items: center;
    height: 6rem;

}

.header .logo h1 {
    font-size: 2rem;
    cursor: default;
}

.header .logo h1 span {
    color: #219ebc;
}

.header .navBar {
    display: flex;
    gap: 1rem;
    text-transform: capitalize;
    flex-direction: row;
}

.header .navBar a {
    display: block;
    font-size: 1.8rem;
    color: white;
}

.header .navBar a:hover {
    color: #219ebc;
}

.header .btnBox {
    display: none;
}

.header .btnBox i {
    font-size: 2rem;
    cursor: pointer;
}

@media (max-width: 768px) {
    .header .btnBox {
        display: block;
    }

    .header .navBar {
        display: flex;
        align-items: center;
        padding: 1rem;
        gap: 1rem;
        text-transform: capitalize;
        flex-direction: column;
        position: fixed;
        top: 6rem;
        left: 0;
        right: 0;
        background: #303030;
        clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
        z-index: 999;
    }

    .header .navBar.active {
        clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
    }
}
</style>