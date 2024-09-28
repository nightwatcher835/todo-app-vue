<template>
  <div>
    <h1>Bem-vindo à página inicial!</h1>
    <p>Este é um exemplo de navegação com Vue Router.</p>
    <router-link to="/todo">Ir para a Lista de Tarefas</router-link>
  </div>
</template>

<script>
export default {
  name: 'HomePage'
};
</script>