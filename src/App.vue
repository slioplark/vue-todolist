<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  }
};
</script>

<style>
@import url("//fonts.googleapis.com/css?family=Roboto:400,500,700,400italic|Material+Icons");
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: auto;
  padding: 16px;
  max-width: 1024px;
  text-align: center;
  color: #2c3e50;
}
body {
  background-color: #202124;
}
img {
  width: 100px;
}
</style>
