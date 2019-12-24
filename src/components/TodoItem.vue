<template>
  <div class="todoList" v-bind:class="{'is-complete':todo.complete}">
    <p>
      <input type="checkbox" v-on:change="onClick" />
      {{todo.title}}
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
</style>