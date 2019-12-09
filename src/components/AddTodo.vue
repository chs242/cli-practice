<template>
  <div class="input-form">
    <input
      type="text"
      v-model="title"
      @keyup.enter="addTodo"
      placeholder="add todo..."
    />
    <input type="submit" value="submit" class="button" @click="addTodo" />
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo() {
      const newTodo = {
        title: this.title,
        completed: false
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
.input-form {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 10px;
}
.button {
  margin-left: 10px;
}
</style>
