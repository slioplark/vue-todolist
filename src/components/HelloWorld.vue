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
      <input type="text" v-model="item.todo" />
      <button @click="remove(item)">remove</button>
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
    remove(data) {
      let idx = this.todoList.indexOf(data);
      this.todoList.splice(idx, 1);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
