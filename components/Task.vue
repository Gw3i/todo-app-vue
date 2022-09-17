<template>
  <li
    :class="`list-group-item list-group-item-success d-flex justify-content-between align-items-center ${
      task.done && 'text-secondary '
    }`"
  >
    {{ task.content }}
    <div class="m-1">
      <button class="btn btn-primary" @click="toggleDone">
        {{ task.done ? 'Undo' : 'Done' }}
      </button>
      <button @click="removeTask" class="btn btn-danger">X</button>
    </div>
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
