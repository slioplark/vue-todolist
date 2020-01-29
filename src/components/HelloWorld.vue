<template>
  <div>
    <h1>{{ name }}</h1>
    <section>
      <input type="text" v-model="todo" placeholder="Add New Item" />
      <button @click="create">add</button>
    </section>
    <section v-if="todoList.length === 0">
      <p>No Data</p>
    </section>
    <section class="item" v-else v-for="item in todoList" :key="item.id">
      <input type="text" v-model="item.todo" />
      <md-button class="md-icon-button md-accent" @click="remove(item)">
        <md-icon>clear</md-icon>
      </md-button>
    </section>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "Todo List",
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
<style scoped lang="scss">
section.item {
  display: flex;
  justify-content: space-between;
  margin: auto;
  width: 512px;
  input {
    outline: none;
    border: none;
    height: 40px;
    font-size: 1.5em;
    background-color: #fafafa;
  }
  & + section.item {
    border-top: 1px solid gray;
  }
}
</style>
