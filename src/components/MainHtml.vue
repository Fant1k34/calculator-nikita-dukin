<template>
  <div class="MyMain">
    <div class="InputClass">
      <input :value="result" v-on:input="result = $event.target.value" >
    </div>
    <table class="input_operations">
      <tr>
        <td>
          <button id="=" :onclick="doMath">
            =
          </button>
        </td>
        <td>
          <button :onclick="deleteAll">
            clear
          </button>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'MainHtml',
  data: function() {
    return { 
      result: "",
    }
  },
  methods: {
    doMath: function() {
      console.log(document.getElementsByTagName("input"));
      let component = document.getElementsByTagName("input")[0];
      this.result = component.value;
      let something;

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
    let component = document.getElementsByTagName("input")[0];
    component.value = "";
    return
    }
  }
}
</script>
<style scoped>
table {
  width: 5%;
  margin-left: 47.5%;
  border: 0ch;
}

</style>
