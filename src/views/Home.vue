<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <!-- <Header /> -->
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Todos from "../components/Todos";
// import Header from "../components/layout/Header";
import AddTodo from "../components/AddTodo";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Todos,
    // Header,
    AddTodo,
  },
  methods: {
    deleteTodo(id) {
      console.log("THi si siid", id);
      axios
        .delete("https://jsonplaceholder.typicode.com/todos/" + id)
        .then(() => {
          this.todos = this.todos.filter((todo) => todo.id != id);
        })
        .catch((error) => {
          console.log("this is error", error);
        });
    },
    addTodo(newTodo) {
      const { title, completed } = newTodo;
      console.log("THi si siid", newTodo);
      axios
        .post("https://jsonplaceholder.typicode.com/todos?_limit=5", {
          title: title,
          completed: completed,
        })
        .then((res) => {
          console.log("THis is re", res.data);
          this.todos = [...this.todos, res.data];
        })
        .catch((error) => {
          console.log("This is error", error);
        });
    },
  },
  data() {
    return {
      todos: [],
    };
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=5")
      .then((res) => {
        console.log("this is res", res.data);
        this.todos = res.data;
      })
      .catch((e) => {
        console.log("This is erroer", e);
      });
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  cursor: pointer;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-break: 1.4;
}
</style>
