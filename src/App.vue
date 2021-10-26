<template>
  <div id="app">
    <HelloWorld msg-value="Welcome to Your Vue.js App" v-on:addEvent="addTodoList" />
    <hr />
    <MyDirective title="동적Tag" :todo-list="todos" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import MyDirective from "./components/MyDirective.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    MyDirective,
  },
  data() {
    return {
      todos: [
        { text: "Vue.js 튜토리얼 작성하기" },
        { text: "Webpack2 알아보기" },
        { text: "사이드 프로젝트 진행하기" },
      ],
    };
  },//data
  methods: {
    addTodoList(todo) {
      const todoObj = {text:todo};
      //todos 배열에 추가
      this.todos.push(todoObj);
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
