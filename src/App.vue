<template>
  <div id="app">
    <h1>Pep Talk Generator</h1>
    <Generator />
  </div>
</template>

<script>
import Generator from "./components/Generator.vue";

export default {
  name: "App",
  components: {
    Generator,
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
