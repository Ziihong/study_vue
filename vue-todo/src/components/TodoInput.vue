<template>
  <div>
    <input type="text" v-model="newTodoInput" />
    <button v-on:click="addTodo">Add</button>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      newTodoInput: "",
    };
  },

  methods: {
    addTodo: function () {
      console.log(this.newTodoInput);
      localStorage.setItem(this.newTodoInput, this.newTodoInput);
      this.clearInput();
    },
    clearInput: function () {
      this.newTodoInput = "";
    },
  },
};
</script>

<style></style>
