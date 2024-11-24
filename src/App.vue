<template>
    <div id="app">

        <BuscadorProducto :juegos="games" @eliminar-juego="eliminarJuego" />
    </div>
</template>

<script>
import BuscadorProducto from './components/buscador.vue';

export default {
    name: 'App',
    components: {
        BuscadorProducto
    },
    data() {
        return {
            games: ["Arena of valor", "Pokemon Unite", "Donkey Kong", "Heroes of the storm", "Valorant"]
        }
    },
    methods: {
        eliminarJuego(index) {
            this.games.splice(index, 1);
        }
    }
}
</script>

<style>
#app {
    text-align: center;
}
</style>