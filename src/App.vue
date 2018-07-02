<template>
  <div id="app" class="text-center">
    <h4 class="text-center border title">Pokedex</h4>
    <PokemonPage />
  </div>
</template>



<script>
  import PokemonPage from './components/PokemonPage.vue'


  export default {
    name: 'App',
    components: {
      PokemonPage
    }
  }
</script>

<style>
  #app {
    
  }

  .title {
    width: 50%;
    height: 40px;
    margin: 0 auto;
  }
</style>

