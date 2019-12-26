<template>
  <div>
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js Talha" /> -->
    <Header />
    <AddTodo v-on:add-todo="addNewTodo" />
    <Todos v-bind:todos="todos" v-on:dltTodo="deleteTodo" />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/layout/Header";
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: "app",
  components: {
    // HelloWorld,
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Talha", complete: false },
        { id: 2, title: "uzair", complete: true },
        { id: 3, title: "nabeel", complete: false }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      // this.todos = this.todos.filter(item => item.id !== id)
      this.todos.map((item, ind) => {
        if (item.id == id) {
          this.todos.splice(ind, 1);
        }
      });
    },
    addNewTodo(e) {
      this.todos = [e, ...this.todos];
    }
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
