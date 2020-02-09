<template>
  <div class="wrapper">
    <div class="campo">
      <div class="logo">Somatória de Primos</div>
      <br><input type="number" @input="atualizarValor" :value="vE" placeholder="Ex: 6" :maxlength="max">
      <div class="descricao" v-if="this.vE == ''">
        Insira um numero
      </div> 
      <div class="descricao" v-else>
        Soma dos {{ this.vE }} primeiros números primos <br>
      </div> 
      <div class="resultado" >
        {{ soma(vE) }}
      </div>

    </div>
    <div class="autor">
    Rickson William - 2020
    </div>
  </div>
</template>

<script>
export default {
  name: 'Primos',
  data(){
    return {
      vE: "",
      max: 4
    }
  },
  methods:{
    soma(quantidade){
      var valor = 2
      var soma = 0 
      var cont = 0
      var isPrimo = null
      while(cont < quantidade){
        isPrimo = true
        if(valor!=1){
          for (var i = 2; i < valor; i++)
            if (valor % i == 0) {
              isPrimo = false
              break
              } 
            if(valor !== 1 && isPrimo){
             isPrimo = true
           }
        }

        if(isPrimo){
          soma = soma + valor
          cont++
        }
        valor++
      }
      return soma
    },
    atualizarValor(event){
      this.vE = event.target.value
      if (this.vE.length <= 4) {
        return;
      }
      this.vE = this.vE.substr(0, 4); 
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
.descricao{
  color: #fff;
  font-size: 60px;
}
.resultado{
  color: #fff;
  font-size: 100px;

}
.autor{
  color: #fff;
  position: fixed;
  bottom: 30px;
  right: 60px;
  font-size: 30px;
}
</style>
