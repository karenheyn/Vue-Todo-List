<template>
  <div id="app">
    <Header />
    <AddToDo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
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
      todos: [
        {
          id: 1,
          title: "Todo One",
          complete: true
        },
        {
          id: 2,
          title: "Todo Two",
          completed: true
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
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
