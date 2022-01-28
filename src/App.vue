<template>
  <div>
    <div class="container">
        <section class="calculadora">
          <Display class="display" :inputNumeros="inputNumeros"/>
         
          <Botoes opBotao="1" class="btn" v-on:click="getNumeros('1')"/>
          <Botoes opBotao="2" class="btn" v-on:click="getNumeros('2')"/>
          <Botoes opBotao="3" class="btn" v-on:click="getNumeros('3')"/>
          <Botoes opBotao="+" class="btn btn-operadores"/>

          <Botoes opBotao="4" class="btn" v-on:click="getNumeros('4')"/>
          <Botoes opBotao="5" class="btn" v-on:click="getNumeros('5')"/>
          <Botoes opBotao="6" class="btn" v-on:click="getNumeros('6')"/> 
          <Botoes opBotao="-" class="btn btn-operadores"/>

          <Botoes opBotao="7" class="btn sete" v-on:click="getNumeros('7')"/>
          <Botoes opBotao="8" class="btn oito" v-on:click="getNumeros('8')"/>
          <Botoes opBotao="9" class="btn nove" v-on:click="getNumeros('9')"/>
          <Botoes opBotao="x" class="btn btn-operadores"/>

          <Botoes opBotao="0" class="btn zero" v-on:click="getNumeros('0')"/>
          <Botoes opBotao="=" class="btn"/>
          <Botoes v-on:click="limpar()" opBotao="C" class="btn"/>
          <Botoes opBotao="÷" class="btn btn-operadores "/>
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
      inputNumeros: "",
      primeirValor:0,
      segundoValor:0,
      result:0,
    };
  },
  methods: {
    getNumeros(tecla){

      this.inputNumeros = ""
      
      if(tecla){
        this.inputNumeros += tecla;
      }
 
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
  background: #1d1d1d;
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
