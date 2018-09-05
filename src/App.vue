<template>
  <div id="app">
    <header class="header">
      Mike's Movies
    </header>
    <SearchBar v-on:addToSearchURL="search"/>
    <MovieList :searchTerm="searchItem"/>


  </div>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import MovieList from "./components/MovieList.vue";
export default {
  name: "app",
  components: {
    SearchBar,
    MovieList
  },
  data: function() {
    return {
      searchItem: ''
    }
  },
  methods: {
    search: function(searchTerm) {
      this.searchItem = searchTerm
      console.log("caught Emit", this.searchItem)
    }
  }
};
</script>

<style>
html {
  height: 100%;
}

body {
  height: 100%;
}

* {
  padding: 0;
  margin: 0;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}

.header {
  display: flex;
  justify-content: center;
  border-bottom: 2px solid #2c3e50;
  font-size: 2em;
}
</style>
