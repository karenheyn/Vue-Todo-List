<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos"></div>
    <h3>{{todo.title}}</h3>
    <h3>hello</h3>
  </div>
</template>

<script>
export default {
  name: "Todos",
  props: ["todos"]
};
</script>

<style scoped>
</style>