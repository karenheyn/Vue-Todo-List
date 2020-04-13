<template>
  <div>
    <form>
      <input type="text" name="title" placeholder="Add Todo..." />
      <button type="submit" class="button">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddToDo"
};
</script>

<style scoped>
form {
  display: flex;
  padding: 5px;
}
input {
  flex: 2;
  padding: 10px;
}
.button {
  flex: 1;
  background: #aaa;
  /* max-width: 55px; */
}
</style>