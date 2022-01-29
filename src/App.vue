<template>
  <div>
    <div class="container">
        <section class="calculadora">
          <Display class="display" :inputNumeros="inputNumeros"/>
         
          <Botoes opBotao="1" class="btn" v-on:click="getNumeros('1')"/>
          <Botoes opBotao="2" class="btn" v-on:click="getNumeros('2')"/>
          <Botoes opBotao="3" class="btn" v-on:click="getNumeros('3')"/>
          <Botoes opBotao="+" class="btn btn-operadores" v-on:click="getOperador('+')"/>

          <Botoes opBotao="4" class="btn" v-on:click="getNumeros('4')"/>
          <Botoes opBotao="5" class="btn" v-on:click="getNumeros('5')"/>
          <Botoes opBotao="6" class="btn" v-on:click="getNumeros('6')"/> 
          <Botoes opBotao="-" class="btn btn-operadores" v-on:click="getOperador('-')"/>

          <Botoes opBotao="7" class="btn sete" v-on:click="getNumeros('7')"/>
          <Botoes opBotao="8" class="btn oito" v-on:click="getNumeros('8')"/>
          <Botoes opBotao="9" class="btn nove" v-on:click="getNumeros('9')"/>
          <Botoes opBotao="x" class="btn btn-operadores" v-on:click="getOperador('x')"/>

          <Botoes opBotao="0" class="btn zero" v-on:click="getNumeros('0')"/>
          <Botoes opBotao="=" class="btn btn-operadores" v-on:click="postIgual()"/>
          <Botoes opBotao="C" class="btn btn-operadores" v-on:click="limpar()" />
          <Botoes opBotao="÷" class="btn btn-operadores " v-on:click="getOperador('÷')"/>
        </section>  
    </div>  
  </div>   
</template>
 
<script>
import Display from './components/Display.vue'
import Botoes from './components/Botoes.vue'

export default {
  name: 'App',
  components: {
    Display,
    Botoes
  },
  data(){
    return{
      inputNumeros: "0",
      primeiroValor:0,
      segundoValor:0,
      operador:"",
      sequencia: 0,
      igual: 0,
      result:0,
    };
  },
  methods: {
    getNumeros(tecla){

        if(tecla === "0" & this.inputNumeros === "" || tecla === "0" & this.inputNumeros === "0"){        
            this.inputNumeros = "0"
        }
        else if (this.inputNumeros === "0" & tecla !== "0") {
            this.inputNumeros = tecla;
        } 
        else{
            this.inputNumeros += tecla;
        }
   
    },
    getOperador(currentOperador) {
      
        if (this.sequencia === 0) {
            this.primeiroValor = parseInt(this.inputNumeros);
            this.operador = currentOperador;
            this.inputNumeros = "";
            this.sequencia++;
        }
        else if (this.igual === 1) {
            this.operador = currentOperador;
            this.igual = 0;
                }
        else if (this.inputNumeros === "") {
            this.operador = currentOperador;
        }
        else {
            this.segundoValor = parseInt(this.inputNumeros);
            
            switch(this.operator){
                case "+" :
                  this.result = this.primeiroValor + this.segundoValor;
                  this.inputNumeros = this.result 
                  this.primeiraValor = this.result;
                  this.operator = currentOperador;
                  this.inputNumeros = "";
                break;
                    
                case "-" :
                  this.result = this.primeiroValor - this.segundoValor;
                  this.inputNumeros = this.result 
                  this.primeiroValor = this.result;
                  this.operator = this.currentOperador;
                  this.inputNumeros = "";
                break;
                    
                case "x" :
                  this.result = this.primeiroValor * this.segundoValor;
                  this.inputNumeros = this.result 
                  this.primeiroValor = this.result;
                  this.operator = this.currentOperador;
                  this.inputNumeros = "";
                break;
                    
                case "÷" :
                  this.result = this.primeiroValor / this.segundoValor;
                  this.inputNumeros = this.result 
                  this.primeiroValor = this.result;
                  this.operator = this.currentOperador;
                  this.inputNumeros = ""; 
                break;
            }
        }  
    },
    postIgual() {
      if (this.sequencia === 0) {
          console.log("entrou no If")
      }
      else if (this.inputNumeros === "") {
          console.log("entrou no else if")
      }
      else {
          this.segundoValor = parseInt(this.inputNumeros);
          this.igual = 1;
          switch(this.operador){
              case "+" :
                this.result = this.primeiroValor + this.segundoValor;
                this.inputNumeros = this.result;
/*                 this.primeiroValor = this.result;
                   this.inputNumeros = ""; */
              break;
                  
              case "-" :
                this.result = this.primeiroValor - this.segundoValor;
                this.inputNumeros = this.result;
/*                 this.primeiroValor = this.result;
                   this.inputNumeros = ""; */
              break;
                  
              case "x" :
                this.result = this.primeiroValor * this.segundoValor;
                this.inputNumeros = this.result;
/*                 this.primeiroValor = this.result;
                   this.inputNumeros = ""; */
              break;
                  
              case "÷" :
                this.result = this.primeiroValor / this.segundoValor;
                this.inputNumeros = this.result;
/*                 this.primeiroValor = this.result;
                   this.inputNumeros = ""; */
              break;
          }
      }
    },
    limpar() {
      this.sequencia = 0;
      this.igual = 0;
      this.inputNumeros = "0";
    }


  }
}
</script>

<style>

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container{
  background: #bbbbbb;
  width: 100vw;
  height: 100vh;
  justify-content: center;
  align-content: center;
  display: grid;
}

.calculadora{
  display: grid;
  height: 480px;
  width: 320px;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(5, 2fr);
}

.display {
  grid-column: 1 / 5;
  background-color: #4A494F;
  opacity: 0.7;
  border: none;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;

}

.zero{
  grid-column: 1 / 2;
}

</style>
