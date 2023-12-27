<template>
  <div class="app-body">
    <TodoView :todos="todos" />
    <TodoForm @submit-todo="addTodo" />
  </div>
</template>
<script>
import TodoForm from "./components/TodoForm.vue";
import TodoView from "./components/TodoView.vue";

export default {
  name: "App",
  components: { TodoView, TodoForm },
  data() {
    return {
      todos: [
        {
          title: "Let's Learn Vue",
          description:
            "VUE.js is one of the most popular JavaScript framework for web application development",
        },
      ],
    };
  },
  methods: {
    addTodo(todo){
      this.todos.push(todo);
    }
  }
};
</script>
<style>
.app-body {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 5rem
}
</style>
