<template>
  <div>
    <h1>{{ name }}</h1>
    <p v-for="item in todoList" :key="item">{{ item }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "Hello World",
      todoList: [1, 2, 3]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
