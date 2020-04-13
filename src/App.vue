<template>
  <div id="app">
    <Header />
    <AddToDo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import axios from "axios";
import AddToDo from "./components/AddToDo";
import Header from "./components/layout/Header";
import Todos from "./components/Todos";

export default {
  name: "app",
  components: {
    Todos,
    Header,
    AddToDo
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  },
  created() {
    axios
      .get("http://jsonplaceholder.typicode.com/todos?_limit=10")
      .then(res => (this.todos = res.data))
      .catch(err => console.log(err));
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0 auto;
  padding: 0;
}
</style>
