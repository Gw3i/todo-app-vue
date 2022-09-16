<template>
  <li
    :class="`list-group-item list-group-item-success ${
      task.done && 'text-secondary'
    }`"
  >
    {{ task.content }}
    <button class="btn btn-primary" @click="toggleDone">
      {{ task.done ? 'Undo' : 'Done' }}
    </button>
    <button @click="removeTask" class="btn btn-danger">Delete</button>
  </li>
</template>

<script>
export default {
  props: ['task'],

  methods: {
    toggleDone(task) {
      this.$store.commit('toggleTask', this.task)
    },
    removeTask(task) {
      this.$store.commit('removeTask', this.task)
    },
  },
}
</script>
