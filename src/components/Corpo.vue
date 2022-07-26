<template>
    <main>
        <div id="cards" v-for="(pokemon, index) in pokemons.results" :key="index"  >
            <Card :nomePokemon="pokemon.name" :numPokedex="index + 1"/>
        </div>
    </main>
</template>

<script>
import api from '../services/api.js';
import Card from './CardPokemon.vue';

export default {
    name: 'corpo',
    components: {
        Card
  },
    data(){
        return{
            pokemons: []
        }
    },
    mounted(){
        api.get('pokemon').then(response => {
            this.pokemons = response.data;
        });
    }
}
</script>

<style scoped>

#cards{
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 20px;
}

</style>