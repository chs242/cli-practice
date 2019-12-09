<template>
  <div id="app">
    <Header />
    <Todos :todos="todos" v-on:del-todo="deleteTodo" />
    <AddTodo v-on:add-todo="addTodo" />
    <Percentage :todos="todos" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";
import AddTodo from "./components/AddTodo";
import Percentage from "./components/Percentage";

export default {
  name: "app",
  components: {
    Header,
    Todos,
    AddTodo,
    Percentage
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "take out the garbage",
          completed: false
        },
        {
          id: 2,
          title: "clean the floor",
          completed: false
        },
        {
          id: 3,
          title: "mow the lawn",
          completed: false
        }
      ],
      percentage: ""
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
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
  font-family: Arial, Helvetica, sans-serif;
}
</style>
