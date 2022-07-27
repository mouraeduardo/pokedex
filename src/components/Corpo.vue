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
        this.AllPokemon();
    },
    methods: {
        searchPokemonCorpo(pokemonTeste) {
            api.get('pokemon/' + pokemonTeste).then(response => {
            this.PesquisaAtivada(pokemonTeste);
            console.log(pokemonTeste);
            this.pokemons = response.data;
        });
        },
        PesquisaAtivada(pokemonPesquisa){
            if(!pokemonPesquisa.length == 0){
                this.pesquisaAtiva = true;
                console.log(this.pesquisaAtiva);
            } else{
                this.AllPokemon();
                this.pesquisaAtiva = false;
            }
        },
        AllPokemon(){
            api.get('pokemon').then(response => {
            this.pokemons = response.data.results;
        });
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