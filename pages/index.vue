<template>
  <main>
    <h1>Todo App</h1>
    <p>Create a list of tasks</p>

    <form>
      <label>
        <input
          type="text"
          placeholder="Add new task"
          v-model="newTask"
          @keypress.enter="addTask"
        />
      </label>
      <button @click="addTask">Add</button>
    </form>
  </main>
</template>

<script>
export default {}
</script>
