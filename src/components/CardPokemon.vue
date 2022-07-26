<template>    
    <div id="CardsPet">
      <div id="card">
        <img id="pokemon-img" :src="this.pokemons.sprites.other.home.front_default" alt="foto pokemon">
        <div id="info-pokemon">
          <label id="nome-pokemon" for="">{{nomePokemon}}</label>
        </div>
      </div>

    </div>
</template>

<script>
import api from '../services/api.js';

export default {
    name : 'CardPokemon',
    props: ['nomePokemon', 'numPokedex'],
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
  border: 2px solid chartreuse;
  width: 200px;
  height: 250px;
  background-color: white;
}

#pokemon-img{
  width: 190px;
  height: 190px;
}

#info-pokemon{
  border: 2px 2px;
  border-color: black;
  display: flex;
  background-color: chartreuse;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 60px;
  border-end-start-radius: 20px;
  border-end-end-radius: 20px;
}

label{
  font-size: 20px;
  font-family: sans-serif;
  padding: 5px;
}

#num-pokedex{

}

</style>