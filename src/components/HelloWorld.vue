<template>
  <div>
    <md-card>
      <md-card-header>
        <h1>{{ name }}</h1>
      </md-card-header>
      <md-card-content>
        <section class="item">
          <input type="text" v-model="todo" placeholder="Add New Item" />
          <md-button class="md-icon-button md-primary" @click="create">
            <md-icon>add</md-icon>
          </md-button>
        </section>
        <section class="item" v-if="todoList.length === 0"></section>
        <section class="item" v-else v-for="item in todoList" :key="item.id">
          <md-checkbox v-model="item.isComplete"></md-checkbox>
          <input type="text" v-model="item.todo" :class="{ line: item.isComplete }" />
          <md-button class="md-icon-button md-accent" @click="remove(item)">
            <md-icon>clear</md-icon>
          </md-button>
        </section>
      </md-card-content>
    </md-card>
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
.md-card {
  margin: 16px auto;
  max-width: 512px;
  min-height: 512px;
  border-radius: 8px;
}
section.item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: auto;
  max-width: 512px;
  input {
    outline: none;
    border: none;
    width: 100%;
    height: 40px;
    font-size: 1.5em;
  }
  input.line {
    text-decoration: line-through;
  }
  & + section.item {
    border-top: 1px solid gray;
  }
}
</style>
