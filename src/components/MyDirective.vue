<template>
  <div>
    <h2>Vue Directive {{ title }}</h2>
    <ul>
      <li>Interpolation = {{ name }}</li>
      <li>v-text 속성 = <span v-text="name"></span></li>
      <li>v-html 속성 = <span v-html="myhtml"></span></li>
      <li>v-show 속성 = <span v-show="isShow" v-html="myhtml"></span></li>
      <li>v-if 속성 = <span v-if="value > 0" v-text="name"></span></li>
    </ul>
    Name : <input type="text" v-model="name" />
    <!-- <input type="text" :value="name" v-on:change=""  />  -->
    <ul>
        <!-- Elements in iteration expect to have 'v-bind:key' directives. -->
        <!-- <li v-for="(todo, idx) in todos" :key="idx"> -->
        <li v-for="todo in todos" :key="todo.id">
            {{todo.text}}
        </li>
    </ul>
    <input type="checkbox" v-model="isShow" />Image 변경 <br/>
    <img :src="isShow ? vuelogo : anglogo" width="200" height="200" />
    <!-- v-bind:src 축약하면 :src -->
    <div>
        Value = {{value}} <br/>
        <button v-on:click="increment">증가</button>
        <button @click="decrement">감소</button>
    </div>
  </div>
</template>
<script>
export default {
  props: ["title"], //부모컴포넌트에서 받은 변수
  data() {
    //자신의 컴포넌트에서 사용하는 변수
    return {
      name: "VueJS",
      myhtml: "<i>Vuejs</i>",
      isShow: false,
      value: 0,
      vuelogo: "https://vuejs.org/images/logo.png",
      anglogo: "https://angular.io/assets/images/logos/angular/angular.svg",
      todos: [
        { id:1, text: "Vue.js 튜토리얼 작성하기" },
        { id:2, text: "Webpack2 알아보기" },
        { id:3, text: "사이드 프로젝트 진행하기" },
      ],
    };
  },//data
  methods: {
    //이벤트 핸들러 함수선언  
    increment() {   //increment: function() {
        this.value++;
    },
    decrement() {
        this.value--;
    }
  } //methods
}; //export 
</script>
