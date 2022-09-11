<template>
  <main>
    <v-card class="pa-5 ma-5">
      <h1>To do list</h1>
      <p>Crie uma nova tarefa</p>
      <div class="create-new">
        <v-text-field type="text" v-model="newTask" placeholder="Add a new task" @keypress.enter="addTask" />
        <v-btn @click="addTask">Adicionar</v-btn>
      </div>
    </v-card>
  </main>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
