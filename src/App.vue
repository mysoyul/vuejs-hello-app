<template>
  <div id="app">
    <HelloWorld msg-value="Welcome to Your Vue.js App" />
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
        { id: 1, text: "Vue.js 튜토리얼 작성하기" },
        { id: 2, text: "Webpack2 알아보기" },
        { id: 3, text: "사이드 프로젝트 진행하기" },
      ],
    };
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
