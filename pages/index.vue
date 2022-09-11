<template>
  <main>
    <v-container class="justify-center">
      <v-card class="mx-auto pa-5" max-width="800">
        <v-card-title>
          <h1>Coisas importantes</h1>
        </v-card-title>
        <v-text-field type="text" class="ma-5" v-model="newTask" placeholder="Descreva a tarefa"
          @keypress.enter="addTask" />
        <v-card-actions>
          <div class="create-new">
            <v-btn @click="addTask" class="primary ml-3">Confirmar</v-btn>
          </div>
        </v-card-actions>
      </v-card>
    </v-container>
    <v-container class="justify-center">
      <v-row v-for="(task,i) in $store.state.tasks" :key="i" class="justify-center">
        <v-col cols="12" sm="8" md="4">
          <Task :task="task" />
        </v-col>
      </v-row>
    </v-container>
  </main>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      newTask: ''
    }
  },
  methods: {
    addTask() {
      if (this.newTask) {
        this.$store.commit('ADD_TASK', this.newTask)
        this.newTask = ''
      }
    }
  }

}
</script>
