<template>
  <div class="todoList" v-bind:class="{'is-complete':todo.complete}">
    <p>
      <input type="checkbox" v-on:change="onClick" />
      {{todo.title}}
      <button @click="$emit('dltTodo', todo.id)" class="del">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    onClick() {
      this.todo.complete = !this.todo.complete;
    }
  }
};
</script>

<style scoped>
.todoList {
  padding: 10px;
  border-bottom: 1px solid black;
  background-color: rgba(92, 90, 88, 0.096);
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>