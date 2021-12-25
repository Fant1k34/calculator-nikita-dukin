<template>
  <div class="hello">

    <input id="ItIs" :value="result" v-on:input="result = $event.target.value" > <!-- v-on:input="result = $event.target.value" -->

    <button id="=" :onclick="doMath">
      =
    </button>

    <button id="clear" :onclick="deleteAll">
      clear
    </button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function() {
    return { 
      result: "",
    }
  },
  methods: {
    doMath: function() {
      // Прошу прощения, но я питонист, поэтому switch не люблю ;)
      var component = document.getElementById("ItIs");
      this.result = component.value;
      var something;
      console.log(something)

      if (this.result.split("").filter(x => (x == "+") || (x == "-") || (x == "-") || (x == "/") || (x == "^")).lenght != 1) {
        component.value = "0"
      }

      if (this.result.includes("+")){
        something = this.result.split("+");
        this.result = parseFloat(something[0]) + parseFloat(something[1]);
        return
      }
      if (this.result.includes("-")){
        something = this.result.split("-");
        this.result = parseFloat(something[0]) - parseFloat(something[1]);
        return
      }
      if (this.result.includes("*")){
        something = this.result.split("*");
        this.result = parseFloat(something[0]) * parseFloat(something[1]);
        return
      }
      if (this.result.includes("/")){
        something = this.result.split("/");
        this.result = parseFloat(something[0]) / parseFloat(something[1]);
        return
      }
      if (this.result.includes("^")){
        something = this.result.split("^");
        this.result = parseFloat(parseFloat(something[0]) ** parseFloat(something[1]));
        return
      }
    },
  deleteAll: function() {
    this.realResult = "";
    this.result = "";
    var component = document.getElementById("ItIs");
    component.value = "";
    return
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
