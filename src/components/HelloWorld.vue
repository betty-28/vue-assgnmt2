<template>
  <div class="movie">
    <h2>{{ movie.name }}</h2>
    <p>Directed By: {{ movie.director }}</p>
  </div>
</template>

<script>
export default {
  props: {
    movie: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.movie {
  margin: 20px;
  padding: 10px;
  border: 1px solid #ccc;
}
</style>
