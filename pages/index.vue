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
      <button class="btn btn-primary" @click.prevent="addTask">Add</button>
    </form>

    <ul>
      <Task v-for="task in $store.state.tasks" :key="task.id" :task="task" />
    </ul>
  </main>
</template>

<script>
import Task from '../components/Task.vue'
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
  components: { Task },
}
</script>
