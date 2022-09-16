<template>
  <main class="d-flex align-items-center flex-column pt-5">
    <h1>Todo App</h1>
    <p>Create a list of tasks</p>

    <form>
      <label class="form-label" for="addTask">
        <input
          id="addTask"
          class="form-control"
          type="text"
          placeholder="Add new task"
          v-model="newTask"
          @keypress.enter="addTask"
        />
      </label>
      <button class="btn btn-primary" @click="addTask">Add</button>
    </form>

    <ul>
      <!-- Task Component-->
    </ul>
  </main>
</template>

<script>
export default {
  data() {
    return {
      newTask: '',
    }
  },
  methods: {
    addTask() {
      if (this.newTask) {
        this.$store.commit('addTask', this.newTask)
        this.newTask = ''
      }
    },
  },
}
</script>
