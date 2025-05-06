<!-- SCRIPT -->
<script setup>
  // Função para validar o formulário
  function validaFormulario(event) {
    alert('Formulário enviado');

    event.preventDefault();
  }
</script>

<!-- HTML -->
<template>
    <form action="https://glaucopereira.com" @submit="validaFormulario">
        <input type="submit" value="Enviar formulário"> &nbsp;
        <button type="submit">Teste Buton</button>
    </form>
    <p>Por qual motivo ele usou um input como button? Pesquisar</p>
    <p>Dica JS: EventpreventDefault -> Evita o acionamento do action no form </p>
</template>