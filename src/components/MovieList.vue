<template lang="pug">
  .movie-list-container
    ul
      li(v-for="movie in movies")
        h1 {{ movie.title }}
        p {{ movie.release_date }}
        img.movie-image(:src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`")
</template>

<script>
export default {
  name: 'movieList',
  props: {
    movies: Array
  }
}
</script>

<style lang="scss" scoped>
.movie-list-container {
  margin: 20px;

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;

    li {

      h1 {
        margin: 0;
      }

      p {
        margin: 0;
      }

      .movie-image {
        height: 300px;
        margin-bottom: 20px;
      }
    }
  }
}

</style>


