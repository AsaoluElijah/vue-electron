<template>
  <div id="app">
    <div class="container">
      <div class="text-center">
        <h2 class="text-center mt-5">Trending Movies 🍿</h2>
        <p>Keep up with the hottest movies that are trending this week.</p>
      </div>

      <div class="my-4">
        <a href="#" @click="getTrendingMovies('day')" class="mx-3 h4">
          Trending today</a
        >
        <a href="#" @click="getTrendingMovies('week')" class="mx-3 h4"
          >This week</a
        >
      </div>

      <div class="row" v-if="movies.length > 0">
        <div class="col-md-3" v-for="(movie, i) in movies" :key="i">
          <movie-card :movie="movie" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MovieCard from "./components/MovieCard.vue";
export default {
  name: "App",
  components: {
    MovieCard,
  },
  data() {
    return {
      movies: [],
      apiKey: "7f7e4a31b7625e58830d55c089d2db11",
    };
  },
  methods: {
    getTrendingMovies(category) {
      return fetch(
        `https://api.themoviedb.org/3/trending/movie/${category}?api_key=${this.apiKey}`
      )
        .then((response) => response.json())
        .then((data) => {
          this.movies = data.results;
        });
    },
  },
  mounted() {
    this.getTrendingMovies("day");
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
