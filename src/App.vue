<template>
  <div id="app">
    <div class="conteudo">
      <div class="calculos">
        <Seculos v-if="this.mostrar" />
        <Primos v-else />
      </div>
      <div class="botao" @click="trocar">
        <div v-if="this.mostrar">Calculadora de numeros primos</div>
        <div v-else>Calculadora de Séculos</div>
      </div>
    </div>
  </div>
</template>

<script>
import Seculos from './components/Seculos.vue'
import Primos from './components/Primos.vue'

export default {
  name: 'App',
  components: {
    Seculos,
    Primos
  },
  data(){
    return{
      mostrar: true
    }
  },
  methods:{
    trocar(){
      this.mostrar = !this.mostrar
    }
  }
}
</script>

<style>
.conteudo{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 600px;
}
.botao{
  color: #fff;
  font-size: 40px;
  border: 1px solid;
  width: 400px;
  margin: 0 auto;
  border-radius: 5px;
}
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
