<template>
    <section class="search_bar">
        <section>Search for your Movie</section>
        <input type=text placeholder="Search by Movie Title" v-model='searchBar' v-on:keyup.enter="enterSearch"/>
    </section>
    
</template>

<script>
export default {
  name: "SearchBar",
  data: function() {
    return {
      searchBar: "",

    };
  },
  methods: {
    enterSearch: function() {
        console.log('search bar works')
    //   let searchURL =
    //     "https://api.themoviedb.org/3/search/movie?api_key=3d986795ed5bf93d949ce7ee0258c436&query=mission&language=en-US&page=1&include_adult=false";
    //   console.log("search bar works");
    //   this.searchBar = "";
    //   fetch(searchURL)
    //     .then(resp => resp.json())
    //     .then(data => {
    //       console.log(data);
    //     });
    }
  }
};
</script>

<style scoped>
.search_bar {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1em;

}

input {
  height: 2em;
  width: 30em;
}
</style>
