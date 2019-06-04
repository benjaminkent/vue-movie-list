<template lang="pug">
  .movie-container
    router-link(to="/") Home
    h1 {{ movie.title }}
    p {{ movie.overview }}
    img.movie-image(:src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`")
</template>

<script>
import axios from 'axios'

export default {
  name: 'Movie',
  data () {
    return {
      movie: {}
    }
  },
  mounted () {
    axios
      .get(`https://api.themoviedb.org/3/movie/${this.$route.params.movieId}?api_key=528804f087c8209bcf748a9147e6c57d&language=en-US`)
      .then(response => this.movie = response.data)
  }
}
</script>

<style lang="scss" scoped>
.movie-container {
  margin: 20px;
}
.movie-image {
  height: 500px;
}
</style>
