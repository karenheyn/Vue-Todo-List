<template>
  <header class="header">
    <h1>TodoList</h1>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </header>
</template>

<script>
export default {
  name: "header"
};
</script>

<style scoped>
.header {
  padding: 10px;
  color: #fff;
  text-align: center;
  background: #333;
}

.header a {
  color: #fff;
}
</style>
