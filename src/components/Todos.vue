<template>
  <div>
    <div v-bind:key="item.id" v-for="item in todos">
      <!-- <h2>{{item.title}}</h2> -->
      <TodoItem v-bind:todo="item" v-on:dltTodo="$emit('dltTodo', item.id)" />
    </div>
  </div>
</template>


<script>
import TodoItem from "./TodoItem";
export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>

<style  scoped>
</style>