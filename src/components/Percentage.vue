<template>
  <div class="percentage">
    <h4>{{ test }} % complete</h4>
  </div>
</template>

<script>
export default {
  name: "Percentage",
  data() {
    return {
      test: 0
    };
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
