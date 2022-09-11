<template>
  <v-card>
    <v-card-title>
      <p>{{ task.content }}</p>
    </v-card-title>
    <v-card-actions>
      <v-btn @click="removeTask" class="primary ml-3">Remover</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: {
      type: Object,
      required: true
    }
  },
  methods: {
    removeTask() {
      this.$store.commit('REMOVE_TASK', this.task)
    }
  }
}
</script>
