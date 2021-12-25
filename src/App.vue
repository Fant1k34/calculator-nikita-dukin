<template>
<p> Калькулятор работает только с простыми действиями: 1 + 2!</p>
  <MyMain v-model:realResult="realResult" @real-result="handleRes" msg="Welcome to Your Vue.js App"/>
    <table class="table_numbers">
      <tr v-for="(post, i) in object" :key="i + 1">
        <td v-for="(post, j) in len_table" :key="j + 1">
          <buttonMy :id="i * table_len_amount + j" />
        </td>
      </tr>
    </table>
    <table class="table_operations">
      <tr>
        <td>  <buttonMy class="plus" :id="'+'">+</buttonMy>  </td>
        <td>  <buttonMy class="minus" :id="'-'">-</buttonMy>  </td>
        <td>  <buttonMy class="multiply" :id="'*'">*</buttonMy> </td>
        <td>  <buttonMy class="divide" :id="'/'">/</buttonMy> </td>
        <td>  <buttonMy class="power" :id="'^'">^</buttonMy>  </td>
      </tr>
    </table>
</template>


<script>
import MyMain from './components/MainHtml.vue'
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
      {number: 2}
    ],
    len_table: [
      {number: 0},
      {number: 1},
      {number: 2}
    ],
    realResult: "",
    something: "",
    table_len_amount: 3,
    };
  },
  components: {
    MyMain,
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

.table_numbers {
  margin-left: 47.25%;
}

.table_operations {
  margin-left: 45.75%;
}


li {
    list-style-type: none;
   }
</style>
