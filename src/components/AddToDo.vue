<template>
  <div>
    <form @submit="addTodo">
      <input
        v-model="title"
        type="text"
        name="title"
        placeholder="Add Todo..."
      />
      <button type="submit" class="button">Submit</button>
    </form>
  </div>
</template>

<script>
import uuid from "uuid";
export default {
  name: "AddToDo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        completed: false
      };
      this.$emit("add-todo", newTodo);
    }
  }
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
