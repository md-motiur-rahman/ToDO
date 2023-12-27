<template>
  <div class="todo_form">
    <form @submit.prevent="onSubmit">
      <label for="title">Title</label>
      <input
        type="text"
        id="title"
        v-model="title"
        placeholder="Todo Title"
      />
      <label for="description">Description</label>
      <textarea
        id="description"
        v-model="description"
        cols="30"
        rows="5"
        placeholder="Description"
      ></textarea>
      <button type="submit">Add Todo</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "TodoForm",
  data() {
    return {
      title: "",
      description: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.title === "" || this.description === "") {
        alert("All fields are required");
        return;
      }
      let todo = {
        title: this.title,
        description: this.description,
      };

      this.$emit("submit-todo", todo);

      this.title = "";
      this.description = "";
    },
  },
};
</script>
<style scoped>
.todo_form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1rem;
  border: 1px solid gray;
  background: #2e2836;
}
form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
form label {
  font-size: 18px;
}
form input {
  font-size: 18px;
  padding: 0.5rem;
}
form textarea {
  font-size: 18px;
  padding: 0.5rem;
}
form button {
  font-size: 18px;
  padding: 0.5rem;
  background: green;
  color: antiquewhite;
  cursor: pointer;
}
</style>
