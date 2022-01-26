<template>
  <div>
    <div class="container">
        <section class="calculadora">
          <Display class="display"/>
         
          <Botoes opBotao="1" class="btn" />
          <Botoes opBotao="2" class="btn"/>
          <Botoes opBotao="3" class="btn"/>
          <Botoes opBotao="+" class="btn btn-operadores"/>

          <Botoes opBotao="4" class="btn"/>
          <Botoes opBotao="5" class="btn"/>
          <Botoes opBotao="6" class="btn"/> 
          <Botoes opBotao="-" class="btn btn-operadores"/>

          <Botoes opBotao="7" class="btn sete"/>
          <Botoes opBotao="8" class="btn oito"/>
          <Botoes opBotao="9" class="btn nove"/>
          <Botoes opBotao="x" class="btn btn-operadores"/>

          <Botoes opBotao="0" class="btn zero"/>
          <Botoes opBotao="=" class="btn"/>
          <Botoes opBotao="C" class="btn"/>
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
