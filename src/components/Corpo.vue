<template>
    <main>
        <SearchBar v-on:searchPokemon="searchPokemonCorpo($event)"/>
        <div id="cards" v-if="this.pesquisaAtiva"  >
            <Card :nomePokemon="pokemons.name"/>
        </div>
        <div id="cards" v-else v-for="(pokemon, index) in pokemons" :key="index"  >
            <Card :nomePokemon="pokemon.name" :numPokedex="index + 1"/>
        </div>
    </main>
</template>

<script>
import api from '../services/api.js';
import Card from './CardPokemon.vue';
import SearchBar from './SearchBar.vue'


export default {
    name: 'corpo',
    components: {
        Card,
        SearchBar
  },
    data(){
        return{
            pokemons: null,
            pesquisaAtiva: false,
        }
    },
    mounted(){
        api.get('pokemon').then(response => {
            this.pokemons = response.data.results;
        });
    },
    methods: {
        searchPokemonCorpo(pokemonTeste) {
            api.get('pokemon/' + pokemonTeste).then(response => {
            this.pesquisaAtiva = true;
            console.log(this.pesquisaAtiva);
            this.pokemons = response.data;
        });
        },
        PesquisaAtivada(){
            this.pesquisaAtiva = true;
        }
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