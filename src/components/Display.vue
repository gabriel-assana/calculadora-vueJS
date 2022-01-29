<template>
  <div>
    <div class="display">{{ inputNumeros }}</div>
  </div>
</template>

<script>
  export default {
    name: 'Display',
    props:{
      inputNumeros: String,
    }
  }
</script>

<style scoped>

.display {
  display:grid;
  justify-items: end;
  width:100%;
  height:100%;
  font-size: 50px;
  color: rgb(255, 255, 255);
  background-color: black;
  padding: 8px
  
}

</style>
