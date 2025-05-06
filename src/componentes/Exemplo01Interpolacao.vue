<!-- Script -->
<script setup>
  // Variáveis
  let nome = 'Rebeca'
  let idade = 30
  let numero1 = 2;
  let numero2 = 5;

</script>

<!-- HTML -->
<template>
  <p>{{ 'Olá ' + nome + ' você tem ' + idade + ' anos.'}}</p>
  <p>{{ numero1 + numero2 }}</p>
</template>