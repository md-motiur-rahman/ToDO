<template>
  <div class="todo_main">
    <h2>ToDo</h2>
    <ul>
        <li v-for="todo in todos" :key="todo.title">
            <h3>{{ todo.title }}</h3>
            <p>{{ todo.description }}</p>
        </li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
  name: "TodoView"
};
</script>
<style scoped>
.todo_main{
    width: 500px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
</style>
