<template>
  <div id="app">
    <div id="nav">
      <Header />
      <router-view />
    </div>
  </div>
</template>

<script>
import Header from "./components/layout/Header";

export default {
  name: "app",
  components: {
    Header
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #1e578f;
  margin: 5px;
}

#nav a.router-link-exact-active {
  color: #42a3b9;
}
</style>
