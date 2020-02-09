# calculo (de ano para seculo / somatória de N numeros primos)
projeto feito por Rickson William
[Link do projeto](https://ricksonwill.github.io/calculos/)
## Funções Principais

1. Para retorna o seculo e diz se ele e **Antes** ou **Depois** de **Cristo**:
```
seculo(anoEntrada){
      var ano = parseInt(anoEntrada)
      var seculo = "1"
      var periodo = ""
      var antesDeCristo = " a. C"
      var depoisDeCristo = " d. C."
      if((ano < 100) && (ano >= 0) || ((ano<0) && (ano > -100) )){
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

```
2. Retorna a somatória dos **N** primeiros numeros primos:
```
somaPrimos(quantidade){
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

```
## Implementações
- [X] Implementção das funções
- [ ] Adicionar Conversor de algarimos Arábico para Romanos



## Para testar a o projeto localmente
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
