<template>
  <div class="wrapper">
    <div class="campo">
      <div class="logo">Calculadora de Século</div>
      <br><input type="number" @input="atualizarValor" :value="anoE" placeholder="Ex: 2020">
      <div class="resultado" v-if="this.anoE == ''">
        Insira um Ano
      </div> 
      <div class="resultado" v-else>
        Século {{ seculo(this.anoE) }} 
      </div> 
    </div>
    <div class="autor">
    Rickson William - 2020
    </div>
  </div>
</template>

<script>
export default {
  name: 'Seculos',
  data(){
    return {
      anoE: "",
    }
  },
  methods:{
    seculo(anoE){
      var ano = anoE
      var seculo = "1"
      var periodo = ""
      var antesDeCristo = " a. C"
      var depoisDeCristo = " d. C."
      if((parseInt(ano) < 100) && (parseInt(ano) >= 0) || ((parseInt(ano)<0) && (parseInt(ano) > -100) )){
        periodo = ano < 0 ? antesDeCristo:depoisDeCristo 
        return seculo + periodo
      }
      var ni = ano.substring(0,(ano.length -2))
      var nf = ano.substr(ano.length - 2)
      if(nf != '00'){
        if(parseInt(ni)<0){
          seculo = parseInt(ni) - 1
        }else{
          seculo = parseInt(ni) + 1
        }
      }else{
        seculo = ni
      }
      if(seculo > 0){
        periodo = depoisDeCristo
        return seculo + periodo
      }else{
        seculo = seculo *  -1
        periodo = antesDeCristo
        return seculo + periodo
      }
    },
    atualizarValor(event){
      this.anoE = event.target.value
    },
  }
}
</script>
<style scoped>
.wrapper{
  display: flex;
  flex-direction: column;
  height: 450px;
}
.logo{
  font-size: 60px;
  color: #fff;
}
.campo{
  margin: auto 0;
}
input{
  margin: 10px 0;
  color: #848484;
  width: 80%;
  max-width: 700px;
  height: 60px;
  text-align: center;
  border-radius: 30px;
  font-size: 25px;
  border: none;
}
.resultado{
  color: #fff;
  font-size: 60px;
}
.autor{
  color: #fff;
  position: fixed;
  bottom: 25px;
  right: 60px;
  font-size: 30px;
}
</style>
