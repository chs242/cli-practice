<template>
  <div>
    <div class="todos-container" v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
      <TodoItemComplete v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
import TodoItemComplete from "./TodoItemComplete.vue"

export default {
  name: "Todos",
  components: {
    TodoItem,
    TodoItemComplete
  },
  props: ["todos"]
};
</script>

<style scoped>
  .todos-container{
    display: flex;
    justify-content: space-between;
    border: 2px solid green;
  }
</style>
