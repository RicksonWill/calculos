<template>
  <div id="app">
    <Seculos/>
  </div>
</template>

<script>
import Seculos from './components/Seculos.vue'

export default {
  name: 'App',
  components: {
    Seculos
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Amatic+SC&display=swap');
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-family: 'Amatic SC', cursive;
}
html, body {
  height: 100%;
  margin: 0;
  padding: 0;
  background-color: #0076FF;
  font-family: 'Amatic SC', cursive;
}
</style>
