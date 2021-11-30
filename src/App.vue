<template>
  <div id="app">
    <Header />
    <div id="selector">
      <FilterAlbum @search="searching" />
    </div>
    <Main :genre="searchOption" />
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
    FilterAlbum,
  },
  data() {
    return {
      searchOption: "",
    };
  },
  methods: {
    searching(genre) {
      this.searchOption = genre;
      console.log(this.searchOption);
    },
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
#selector {
  background-color: rgba(30, 45, 59, 255);
}
* {
  margin: 0;
}
</style>
