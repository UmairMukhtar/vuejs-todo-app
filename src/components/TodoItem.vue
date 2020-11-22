<template>
  <div>
    <p
      class="todo-item slideUp"
      v-bind:class="{ 'is-complete': todo.completed }"
    >
      <input v-on:change="markComplete" type="checkbox" />
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="delete">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}
.delete {
  background: red;
  border: red;
}
</style>
