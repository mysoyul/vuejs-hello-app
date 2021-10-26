<template>
  <div id="app">
    <HelloWorld msg-value="Welcome to Your Vue.js App"/>
    <hr />
    <MyDirective title="동적Tag" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MyDirective from './components/MyDirective.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    MyDirective
  }
}
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
