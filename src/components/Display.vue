<template>
  <div>
    <div class="display">{{ inputNumeros }}</div>
  </div>
</template>

<script>
  export default {
    name: 'Display',
    props:{
      inputNumeros: Number
    }
  }
</script>

<style scoped>

.display {
  color: rgb(255, 251, 251);
  width:100%;
  height:100%;
  font-size: 50px;
}

</style>
