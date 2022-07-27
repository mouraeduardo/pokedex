<template>
  <div id="app">
    <Header/>
    <Corpo />
  </div>
</template>

<script>
import './styles/global.css'
import Header from './components/Header.vue'
import Corpo from './components/Corpo.vue'

export default {
  name: 'App',
  components: {
    Header,
    Corpo,
  }
}
</script>

<style > 

</style>
