<template lang="pug">
  .home-container
    Hero(
      :posters="posters"
      :randomNumber="randomNumber"
    )
    MovieList(:movies="movies")
</template>

<script>
import axios from 'axios'
import MovieList from '../components/MovieList'
import Hero from '../components/Hero'

export default {
  name: 'home',
  components: {
    MovieList,
    Hero
  },
  data () {
    return {
      movies: [],
      posters: [],
      randomNumber: null
    }
  },
  mounted () {
    axios
      .get(' https://api.themoviedb.org/3/movie/now_playing?api_key=528804f087c8209bcf748a9147e6c57d&language=en-US&page=1')
      .then(response => {
        let allPosters = response.data.results.map(movie => {
          return movie.poster_path
        })
        this.movies = response.data.results,
        this.posters = allPosters,
        this.randomNumber = Math.floor(Math.random() * allPosters.length)
      })
  }
}
</script>
