<template>
  <div>
    <h1>Lista de Tarefas</h1>
    <input v-model="newTask" @keyup.enter="addTask" placeholder="Adicione uma nova tarefa" />
    <button @click="addTask">Adicionar</button>

    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <input type="checkbox" v-model="task.completed" />
        <span :class="{ completed: task.completed }">{{ task.text }}</span>
        <button @click="removeTask(index)">Remover</button>
      </li>
    </ul>

    <router-link to="/">Voltar para a Página Inicial</router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
      tasks: []
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim()) {
        this.tasks.push({ text: this.newTask, completed: false });
        this.newTask = "";
      }
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    }
  }
};
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>