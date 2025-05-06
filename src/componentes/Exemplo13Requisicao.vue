<!-- SCRIPT -->
<script setup>

  // Importações
  import{ onMounted, ref } from 'vue';
  
  // vetor contendo as postagens
  let vetor = ref([]);

  // GET
  onMounted(() => {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then(retorno => retorno.json())
        .then(retorno => vetor.value = retorno)
  });

  // POST
  function criarPost() {
  fetch('https://jsonplaceholder.typicode.com/posts', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      title: 'Novo título',
      body: 'Conteúdo do novo post',
      userId: 1
    })
  })
    .then(res => res.json())
    .then(data => {
      console.log('Post criado:', data);
      vetor.value.push(data);
    });
}

// PUT
function atualizarPost(id) {
  fetch(`https://jsonplaceholder.typicode.com/posts/${id}`, {
    method: 'PUT',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      id: id,
      title: 'Título atualizado',
      body: 'Texto atualizado',
      userId: 1
    })
  })
    .then(res => res.json())
    .then(data => {
      console.log('Post atualizado:', data);
    });
}

// Patch - > Atualizar parcialmente (não conheço esse)
function editarPost(id) {
  fetch(`https://jsonplaceholder.typicode.com/posts/${id}`, {
    method: 'PATCH',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      title: 'Título modificado'
    })
  })
    .then(res => res.json())
    .then(data => {
      console.log('Título atualizado:', data);
    });
}

// Delete
function deletarPost(id) {
  fetch(`https:/jsonplaceholder.typicode.com/posts/${id}`, {
    method: 'DELETE'
  })
    .then(() => {
      console.log(`Post ${id} excluído`);
      vetor.value = vetor.value.filter(post => post.id !== id);
    });
}
      
</script>

<!-- HTML -->
<template>
    <h1>Requisições</h1>

    <table>
      <tr v-for="v in vetor">
        <td>{{ v.id }}</td>
        <td>{{ v.userId }}</td>
        <td>{{ v.title }}</td>
        <td>{{ v.body }}</td>
      </tr>
    </table>
</template>