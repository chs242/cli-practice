<template>
  <div id="app">
    <Header />
    <h3 v-if="todos.length === 0">Add somthing to your Todo-LIst...</h3>
    <Todos :todos="todos" v-on:del-todo="deleteTodo" />
    <p class="percentag-done">{{ percentageDone }}% done...</p>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";

export default {
  name: "app",
  components: {
    Header,
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "todo one",
          completed: false
        },
        {
          id: 2,
          title: "todo two",
          completed: false
        },
        {
          id: 3,
          title: "todo three",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  },
  computed: {
    percentageDone() {
      return Math.round(
        (100 / this.todos.length) *
          this.todos.filter(todo => todo.completed).length
      );
    }
  }
};
</script>

<style>
* {
  box-shadow: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial Helvetica sans-serif;
}
</style>
