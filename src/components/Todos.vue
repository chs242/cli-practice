<template>
  <div class="container">
    <div class="oncompleted">
      Oncompleted:
      <TodoItem
        v-for="todo in oncompletedTodos"
        v-bind:key="todo.id"
        v-bind:todo="todo"
        v-on:del-todo="$emit('del-todo', todo.id)"
      />
    </div>
    <div class="completed">
      Completed:
      <TodoItem
        v-for="todo in completedTodos"
        :key="todo.id"
        :todo="todo"
        v-on:del-todo="$emit('del-todo', todo.id)"
      />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"],
  computed: {
    completedTodos() {
      return this.todos.filter(todo => todo.completed);
    },
    oncompletedTodos() {
      return this.todos.filter(todo => !todo.completed);
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
}
</style>