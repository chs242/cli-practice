<template>
    <div class="todo-item" :class="{ 'is-complete': todo.completed }">
    <p>
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="del">X</button>
    </p>
  </div>
</template>

<script>
export default {
    name: "TodoItemComplete",
    props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
}
</script>

<style scoped>
    .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border: 1px solid green;
    width: 50%;
    visibility: hidden;
    }

    .is-complete {
    text-decoration: line-through;
    visibility: visible;
    }

    .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
    }
</style>