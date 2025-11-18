<template>
  <div id="app">
    <Header logo="Fares" />
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
import Header from "./components/global/header.vue";

export default {
  name: "App",
  components: {
    Header,
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
  color: #2c3e50;
}
main {
  padding: 2rem;
}
</style>
