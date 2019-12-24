<template>
  <div>
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js Talha" /> -->
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Todos from "./components/Todos";

export default {
  name: "app",
  components: {
    // HelloWorld,
    Todos
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Talha", complete: false },
        { id: 2, title: "uzair", complete: true },
        { id: 3, title: "nabeel", complete: false }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
