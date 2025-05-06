<!-- SCRIPT -->
<script setup>
  // Variável
  let exibir = true;  
</script>


<!-- HTML -->
<template>
    <h1 v-if="exibir">Hello, world!</h1>
    <h1 v-else>Outro</h1>
</template>