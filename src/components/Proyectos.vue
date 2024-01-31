<script setup>
import { datosP } from './datosProeyctos';

</script>
<template>
    <div class="proyectoBox">
        <div class="proyectoTitulo">
            <h2>lista de proyectos</h2>
        </div>
        <div class="proyectoCardBox">

            <div v-for="peli in datosP" class="proyectoCard">
                <div class="proyectoCardImg">
                    <img v-bind:src="peli.imagen" alt="">
                </div>
                <div class="proyectoText">
                    <span>{{ peli.nombre }}</span>
                    <p>{{ peli.detalles }}</p>
                    <small> <span>precio: </span><b>S/</b>{{ peli.precio }}</small>
                </div>
                <div class="btnBox">

                    <button v-bind:class="[peli.disponible ? '' : 'btnojo']"> {{ peli.disponible ? 'disponible' :
                        'no disponible' }} </button>

                    <button class="btnLink">
                        <a v-bind:href="peli.url" target="_blank"><i class="bi bi-box-arrow-up-right"></i> Ver</a>
                    </button>
                </div>
            </div>

        </div>
    </div>
</template>
<style scoped>
.proyectoBox {
    padding: 2rem;
}

.proyectoBox .proyectoTitulo {
    text-align: center;
    padding-bottom: 2rem;
}

.proyectoBox .proyectoTitulo h2 {
    font-size: 2rem;
    text-transform: capitalize;
    cursor: default;
}

.proyectoBox .proyectoCardBox {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-auto-rows: auto;
    gap: 2rem;
}

.proyectoBox .proyectoCardBox .proyectoCard {
    display: flex;
    flex-direction: column;
    align-items: center;
    /* background-color: blueviolet; */
    border: 1px solid #ccc;
    border-radius: 1rem;
    position: relative;
    padding-bottom: 4rem;
}

.proyectoBox .proyectoCardBox .proyectoCard .proyectoCardImg img {
    width: 100%;
    border-radius: 1rem 1rem 0 0;

}

.proyectoBox .proyectoCardBox .proyectoCard .proyectoText {
    padding: 1rem;
}

.proyectoBox .proyectoCardBox .proyectoCard .proyectoText span {
    font-size: 1.7rem;
    color: #219ebc;
    text-transform: capitalize;
}

.proyectoBox .proyectoCardBox .proyectoCard .proyectoText p {
    font-size: 1.4rem;
}

.proyectoBox .proyectoCardBox .proyectoCard .proyectoText small {
    font-size: 1.6rem;
}

.proyectoBox .proyectoCardBox .proyectoCard .proyectoText small span {
    color: orange;
    text-transform: capitalize;
}

.proyectoBox .proyectoCardBox .proyectoCard .proyectoText small b {
    color: #219ebc;
}

.proyectoBox .proyectoCardBox .proyectoCard .btnBox {
    position: absolute;
    bottom: 1rem;
}

.proyectoBox .proyectoCardBox .proyectoCard .btnBox .btnLink {
    margin-left: .7rem;
}
.proyectoBox .proyectoCardBox .proyectoCard .btnBox .btnLink a {
    color: white;
    padding: .3rem;
}

.proyectoBox .proyectoCardBox .proyectoCard button {
    padding: .5rem;
    border-radius: 1rem;
    border: none;
    font-size: 1.6rem;
    text-transform: capitalize;
    background-color: #0077b6;
    color: white;
    cursor: pointer;

}

.proyectoBox .proyectoCardBox .proyectoCard button.btnojo {
    background-color: #c1121f;
}

.proyectoBox .proyectoCardBox .proyectoCard button.btnojo:hover {
    background-color: #780000;
}

.proyectoBox .proyectoCardBox .proyectoCard button:hover {
    background-color: #2a9d8f;
}
</style>