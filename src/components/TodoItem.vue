<template>
  <div class="todo-item" v-bind:class="{'complete':todo.complete}">
    <p>
      {{todo.title}}
      <input type="checkbox" name="checkbox" v-on:change="markComplete" />
      <button @click="$emit('del-todo', todo.id)" class="delete">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.complete = !this.todo.complete;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px solid black;
}

.complete {
  text-decoration: line-through;
}
</style>