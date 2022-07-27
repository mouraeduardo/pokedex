<template>
    <div class="conteiner">
        <div class="pesquisar-box">
            <input v-model="pokemonSearch" class="pesquisar" type="text" placeholder="Buscar pokemon por nome" />
            <button class="img-pesquisar" @click="$emit('searchPokemon', pokemonSearch)">
            <img
                src="https://cdn-icons-png.flaticon.com/512/622/622669.png"
                alt="lupa"
                width="25px"
                height="25px"
            />
            </button>
        </div>
    </div>
</template>

<script>
export default {
    name : 'SearchBar',
    emits: ['searchPokemon'],
    data() {
        return {
            pokemonSearch: ""
        }
    }
}
</script>

<style scoped>
.pesquisar-box {
  margin: 20px;
  border: 1px solid black;
  border-radius: 40px;
  width: 600px;
  height: 40px;
  padding: 3px;
  padding-left: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.pesquisar {
  border: none;
  background: none;
  outline: none;
  font-size: 20px;
  line-height: 40px;
}
.img-pesquisar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.conteiner{
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>

