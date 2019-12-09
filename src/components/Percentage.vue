<template>
  <div class="percentage">
    <h4>{{ percentage }} % complete</h4>
  </div>
</template>

<script>
export default {
  name: "Percentage",
  props: {
    todos: Object
  },
  data() {
    return {
      test: 0
    };
  },
  computed: {
    percentage() {
      return Math.round(
        (100 / this.todos.length) *
          this.todos.filter(todo => todo.completed).length
      );
    }
  }
};
</script>

<style scoped>
.percentage {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 10px;
}
</style>
