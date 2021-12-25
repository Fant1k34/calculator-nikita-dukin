<template>
  <button class="buttonMy" :onclick="writeNumber">
    {{ id }}
  </button>
</template>

<script>
export default {
  name: 'buttonMy',
  props: {
    buttonValue: {
      type: String,
      default: "1"
    },
    id: {
      default: "",
    }
  },
  methods: {
    writeNumber: function(){
    var component = document.getElementById("ItIs");
    component.value += this.id;
    // console.log(component);
    // component.textContent += this.id;
  }
  }
}
</script>

<style>
</style>
