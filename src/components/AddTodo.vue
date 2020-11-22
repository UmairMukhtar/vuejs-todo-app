<template>
  <header class="header">
    <form @submit="addTodo">
      <input type="text" v-model="title" placeholder="Add Todo..." />
      <input
        type="submit"
        value="Submit"
        placeholder="Add Todo..."
        class="btn"
      />
    </form>
  </header>
</template>

<script>
// import uuid from "uuid";
import { v1 as uuidv1 } from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      console.log("This is it");
      const newTodo = {
        id: uuidv1(),
        title: this.title,
        completed: false,
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}
</style>
