<template>
    <div>
        <div v-for="(pokemon, index) in pokemons.results" :key="index"  >
            <Card :nomePokemon="pokemon.name"/>
        </div>
    </div>
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


</style>