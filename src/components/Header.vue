<template>
  <header class="header">
    <h1>오늘의 할 일</h1>
    <input 
      class="new-todo" 
      autofocus 
      autocomplete="off" 
      placeholder="What needs to be done?"
      v-model="text"
      @keypress="handleTodo"
    >
  </header>
</template>

<script>
export default {
  data() {
    return {
      text: ""
    };
  },
  methods: {
    handleTodo({ keyCode }) {
      const { text } = this;

      if (keyCode === 13 && text !== "") {
        this.$emit("insertTodo", text);
        this.text = "";
      }
    }
  }
};
</script>

<style>
h1 {
  position: absolute;
  top: -115px;
  width: 100%;
  font-size: 50px;
  font-weight: bold;
  text-align: center;
  color: rgba(55, 89, 238, 0.75);
  -webkit-text-rendering: optimizeLegibility;
  -moz-text-rendering: optimizeLegibility;
  text-rendering: optimizeLegibility;
}
</style>