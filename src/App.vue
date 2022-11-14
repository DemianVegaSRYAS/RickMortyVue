<template>
  <div id="app">
    <!-- <userName /> -->
    <RickAndMorty/>
  </div>
</template>

<script>
// import userName from './components/userName.vue'
import RickAndMorty from './components/rickmorty.vue';
export default {
  name: 'App',
  components:{
    RickAndMorty
  }
}
</script>

<style>
body{
  background-color: rgb(219, 219, 219);
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 97vh;
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
