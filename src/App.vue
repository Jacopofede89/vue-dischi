<template>
  <div id="app">
    <Header/>
    <Main @search="searching"/>
    <FilterAlbum :Object="search"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import FilterAlbum from "./components/FilterAlbum.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
    FilterAlbum
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
*{
  margin:0;
}
</style>
