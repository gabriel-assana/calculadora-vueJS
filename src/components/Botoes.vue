<template>
    <div>
      <button class="btn"> {{ opBotao }} </button>
    </div>
</template>

<script>
  export default {
    name: 'Botoes',
    props:{
      opBotao: String
    },  
    data(){
      return{
        valorAtual: 0,
        result:0,
      }
    },
  methods: {
    dividir(){
      
    }
  }
}
</script>

<style>

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
  background-color: #F1A23D;
}

</style>