<template>
    <div>
      <button class="btn"> {{opBotao}} </button>
    </div>
</template>

<script>
  export default {
    name: 'Botoes',
    props:{
      opBotao: String
    } 
}
</script>

<style scoped>

.btn{
  color: white;
  width:100%;
  height:100%;
  font-size: 20px;
  cursor: pointer;
  outline: none;
  background-color: #747474;
}

.btn:hover{
  opacity: 0.9;
}

.btn-operadores button{
  background-color: #f88d00;
}

</style>