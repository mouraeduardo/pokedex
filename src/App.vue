<template>
  <div id="app">
    <Header/>
    <SearchBar/>
    <Corpo />
  </div>
</template>

<script>
import './styles/global.css'
import Header from './components/Header.vue'
import Corpo from './components/Corpo.vue'
import SearchBar from './components/SearchBar.vue'

export default {
  name: 'App',
  components: {
    Header,
    Corpo,
    SearchBar
  }
}
</script>

<style > 

</style>
