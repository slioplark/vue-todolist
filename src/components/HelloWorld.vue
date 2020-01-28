<template>
  <div>
    <h1>{{ name }}</h1>
    <section>
      <input type="text" v-model="todo" />
      <button @click="create">add</button>
    </section>
    <section v-if="todoList.length === 0">
      <p>No Data</p>
    </section>
    <section v-else v-for="item in todoList" :key="item.id">
      <p>{{ item.todo }}</p>
      <button @click="remove(item.id)">remove</button>
    </section>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "Hello World",
      todo: "",
      todoList: []
    };
  },
  methods: {
    create() {
      this.todoList.push({
        id: new Date().getTime(),
        todo: this.todo
      });
      this.todo = "";
    },
    remove(id) {
      let obj = this.todoList.find(item => item.id === id);
      let idx = this.todoList.indexOf(obj);
      this.todoList.splice(idx, 1);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
