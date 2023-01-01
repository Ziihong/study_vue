<template>
  <div class="inputBox">
    <input type="text" v-model="newTodoInput" v-on:keyup.enter="addTodo" />
    <span class="addContainer" v-on:click="addTodo">
      <i class="fas fa-plus addBtn"></i>
    </span>
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
      if (this.newTodoInput !== "") {
        this.$emit("addNewItem", this.newTodoInput); // 하위 컴포넌트에서 발생한 이벤트를 상위 컴포넌트에 전달
        this.clearInput();
      }
    },
    clearInput: function () {
      this.newTodoInput = "";
    },
  },
};
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #6478fb, #8763fb);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>
