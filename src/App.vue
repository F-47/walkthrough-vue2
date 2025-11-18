<template>
  <div id="app">
    <Header logo="Fares" />
    <Products />
  </div>
</template>

<script>
import Products from "./components/Products.vue";
import Header from "./components/global/header.vue";

export default {
  name: "App",
  components: {
    Header,
    Products,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
