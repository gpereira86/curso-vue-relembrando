<!-- Script -->
<script setup>
  // Variáveis
  let nome = 'Alice'
  let idade = 25
  let numero1 = 10;
  let numero2 = 5;

</script>

<!-- HTML -->
<template>
  <p>{{ 'Olá ' + nome + ' você tem ' + idade + ' anos.'}}</p>
  <p>{{ numero1 + numero2 }}</p>
</template>