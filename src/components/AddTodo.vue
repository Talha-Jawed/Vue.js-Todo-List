<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" placeholder="Enter Todo..." />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      if (this.title) {
        var newTodo = {
          id: Math.floor(Math.random() * 1000 + 1),
          title: this.title,
          complete: false
        };
        this.$emit("add-todo", newTodo);
        this.title = "";
      } else {
        alert("Please Enter Todo");
      }
    }
  }
};
</script>

<style  scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>