<!-- SCRIPT -->
<script setup>
  
  // Função
  function mensagem() {
    alert('Trabaqlhando com eventos de clique!');
  }

</script>

<!-- HTML -->
<template>
    <button @click="mensagem">Clique Aqui</button>
</template>