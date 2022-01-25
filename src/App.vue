<template>
  <div>
    <div class="calculadora">
        <Display class= "display"/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
        <Botoes/>
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
.calculadora{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
