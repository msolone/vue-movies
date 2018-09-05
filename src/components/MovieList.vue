<template>

<ul class="movie_list">
    <li v-for="movie in movieData" v-bind:key="movie.id">
        <img :src="getImageURL(movie.poster_path)" alt="Movie Poster">
    </li>
</ul>   

</template>

<script>
export default {
  name: "MovieList",
  data: function() {
    return {
      movieData: []
    };
  },
  mounted: function() {
    console.log("hello");
    const popularURL = 'https://api.themoviedb.org/3/movie/popular?api_key=3d986795ed5bf93d949ce7ee0258c436&language=en-US&page=1' 
    fetch(popularURL)
    .then(resp => resp.json())
    .then(data => {
    console.log(data.results)
    this.movieData = data.results
    })
  },
  methods: {
      getImageURL(poster_path) {
         return `https://image.tmdb.org/t/p/w500/${poster_path}`
      }
  }
};

</script>

<style>
.movie_list {
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
img {
    height: 12em;
    width: 10em;
    padding: 0 0.2em;
}

</style>
