<template>
  <div id="app">
    <Header />
    <Typing/>
    <Instruction />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Typing from "@/components/Typing.vue";
import Instruction from "@/components/Instruction.vue";
export default {
  name: "app",
  components: {
    Header,
    Typing,
    Instruction
  },
  data() {
    return {
      
    };
  }
};
</script>

<style>
body {
  background: #6c757d;
  color: #fff;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
