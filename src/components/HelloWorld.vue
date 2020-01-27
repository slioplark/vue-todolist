<template>
  <div>
    <h1>{{ name }}</h1>
    <section v-if="todoList.length === 0">
      <p>尚無資料</p>
    </section>
    <section v-else>
      <p v-for="item in todoList" :key="item">{{ item }}</p>
    </section>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "Hello World",
      todoList: []
    };
  },
  create() {},
  update() {},
  delete() {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
