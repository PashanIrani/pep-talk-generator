<template>
  <div id="app">
    <img src="/hippo.svg" alt="" srcset="" id="logo" />
    <h1><span>Shitty</span> Pep-Talk Generator</h1>
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
@font-face {
  font-family: "Vintage";
  src: url("/Franchise.ttf") format("truetype");
}

body {
  background-color: #e0d3bc;
}
#app {
  text-align: center;
  color: #2c3e50;
  margin: auto;
  margin-top: 60px;
  font-size: 30px;
  max-width: 500px;
}

h1 {
  font-family: Vintage, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 60px;
}
h1 > span {
  color: #c20000;
}

img#logo {
  width: 150px;
}
</style>
