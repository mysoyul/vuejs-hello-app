<template>
  <div class="hello">
    <h1>{{ msgValue }}</h1>
    Name : <input type="text" v-model="todo" />
    <!-- <input type="text" :value="todo" v-on:change=""  />  -->
    <button v-on:click="addTodo">추가</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: ["msgValue"], //msg-value (x)
  data() {
    return {
      todo: ''
    }
  },  //data
  methods: {
    addTodo() {
      //Click 이벤트가 발생했음을 App 부모 컴포넌트에 알려주기
      //Event이름은 addEvent 입니다. 알려주는 것임
      this.$emit("addEvent", this.todo);
      console.log(this.todo);
      this.todo = '';
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
