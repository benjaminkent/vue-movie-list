<template lang="pug">
  .hero-container
    img.hero-image(
      :src="`https://image.tmdb.org/t/p/w500${posters[randomNumber]}`"
    )
</template>

<script>
export default {
  name: 'hero',
  props: {
    posters: Array,
    randomNumber: Number
  }
}
</script>

<style lang="scss" scoped>
.hero-container {
  display: flex;
  justify-content: center;
  padding: 50px 0;
}
.hero-image {
  height: 400px;
}
</style>

