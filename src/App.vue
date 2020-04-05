<template>
  <div id="app">
    <section class="todoapp">
      <Header @insertTodo="insertTodo" />
      <Todo :todos="todos" @removeTodo="removeTodo" @updateDone="updateDone"/>
      <Footer/>
    </section>
  </div>
</template>

<script>
import "./assets/css/main.css";

import Header from "./components/Header";
import Todo from "./components/Todo";
import Footer from "./components/Footer";

export default {
  components: {
    Header,
    Todo,
    Footer
  },
  data() {
    return {
      todos: [
        {
          id: new Date(),
          text: "Vue 공부하기",
          isDone: true
        },
        {
          id: new Date() + 1,
          text: "치킨 먹기",
          isDone: false
        }
      ]
    };
  },
  methods: {
    insertTodo(text) {
      this.todos = [
        ...this.todos, // 기존의 배열에 새로운 todo 를 추가합니다.
        {
          // id, isDone 의 경우 같은 포맷을 유지하기 때문에 새로 받지 않습니다. 
          id: new Date().getTime(), 
          text, // 유동적인 text 값만 받습니다.
          isDone: false
        }
      ];
    },
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    updateDone(id) {
      const todos = [...this.todos];
      const todo = todos.find(todo => todo.id === id);

      if (todo) {
        todo.isDone = !todo.isDone;
        this.todos = todos;
      }
    }
  }
};
</script>

<style>
</style>