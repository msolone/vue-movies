<template>
    <section class="search_bar">
        <section>Search for your Movie</section>
        <input type=text placeholder="Search by Movie Title" v-model='searchBarInput' v-on:keyup.enter="enterSearch"/>
    </section>
    
</template>

<script>
export default {
  name: "SearchBar",
  data: function() {
    return {
      searchBar: "",
      searchBarInput: ""
    };
  },
  methods: {
    enterSearch: function() {
        this.searchBar = this.searchBarInput
        console.log('search bar works')

        this.$emit('addToSearchURL', this.searchBar)

  }
}
}
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
