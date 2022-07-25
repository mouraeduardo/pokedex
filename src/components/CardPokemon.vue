<template>    
    <div id="CardsPet">
      <div id="card">
        <img id="pokemon-img" :src="this.pokemons.sprites.other.home.front_default" alt="foto pokemon">
        <label for="">{{nomePokemon}}</label>
      </div>

    </div>
</template>

<script>
import api from '../services/api.js';

export default {
    name : 'CardPokemon',
    props: ['nomePokemon'],
    data(){
      return{
        pokemons: [],
        ativou: false
      }
    },
    mounted(){
        api.get('pokemon/' + this.nomePokemon).then(response => {
            this.pokemons = response.data;
        });
    },
    methods:{
      ativar: function () {
        this.ativou = !this.ativou;
      }

    }
}
</script>

<style scoped>

#card{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-radius: 20px;
  border-color: blue;
  width: 200px;
  height: 250px;
  background-color: white;
}

#pokemon-img{
  width: 190px;
  height: 190px;
}


</style>