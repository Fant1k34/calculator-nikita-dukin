<template>
  <HelloWorld v-model:realResult="realResult" @real-result="handleRes" msg="Welcome to Your Vue.js App"/>
  <ul>
  
  <li v-for="(post, i) in object" :key="i + 1">
    <buttonMy :id="i" />
  </li>
  <buttonMy :id="'+'">+</buttonMy>
  <buttonMy :id="'-'">-</buttonMy>
  <buttonMy :id="'*'">*</buttonMy>
  <buttonMy :id="'/'">/</buttonMy>
  <buttonMy :id="'^'">^</buttonMy>
  </ul>
  <p> Калькулятор работает только с простыми действиями: 1 + 2!</p>
</template>


<script>
import HelloWorld from './components/HelloWorld.vue'
import buttonMy from './components/Button.vue'

export default {
  name: 'App',
  props:{
    dopResult: {
      type: String,
      default: ""
    }
  },
  data: function() {
    return {
    object: [
      {number: 0},
      {number: 1},
      {number: 2},
      {number: 3},
      {number: 4},
      {number: 5},
      {number: 6},
      {number: 7},
      {number: 8},
      {number: 9}
    ],
    realResult: "",
    something: "",
    };
  },
  components: {
    HelloWorld,
    buttonMy
  },
  methods: {
    writeNumber: function(){
    this.result += this.id;
    }
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

li {
    list-style-type: none; /* Убираем маркеры */
   }
</style>
