<template lang="pug">
  .home-container
    MovieList(:movies="movies")
</template>

<script>
import axios from 'axios'
import MovieList from '../components/MovieList'

export default {
  name: 'home',
  components: {
    MovieList
  },
  data () {
    return {
      movies: []
    }
  },
  mounted () {
    axios
      .get(' https://api.themoviedb.org/3/movie/now_playing?api_key=528804f087c8209bcf748a9147e6c57d&language=en-US&page=1')
      .then(response => this.movies = response.data.results)
  }
}
</script>
