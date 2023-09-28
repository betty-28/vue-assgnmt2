<template>
  <div class="app">
    <h1>Movie Information</h1>
    <input v-model="searchQuery" placeholder="Search by name or director" />
    <div class="movies" text-align = "left">
      <HelloWorld
        v-for="movie in filteredMovies"
        :key="movie.id"
        :movie="movie"
      />
      <div>
        <ol>
          <li v-for="(movie, index) in filteredMovies" :key="index">{{ movie.title }} - Directed by {{ movie.director }}</li>
        </ol>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue' // Import the Movie component

export default {
  data () {
    return {
      movies: [
        {'id': 1, 'director': 'James Cameroon', 'title': 'Titanic'},
        {'id': 2, 'director': 'James Cameroon', 'title': 'The Terminator'},
        {'id': 3, 'director': 'James Cameroon', 'title': 'Avatar'},
        {'id': 4, 'director': 'Rajamouli', 'title': 'Baahubali'},
        {'id': 5, 'director': 'Rajamouli', 'title': 'RRR'},
        {'id': 6, 'director': 'Rajamouli', 'title': 'Avatar'},
        {'id': 7, 'director': 'Raman H S', 'title': 'Guardians Of Galaxy'},
        {'id': 9, 'director': 'Christopher Nolan', 'title': 'Inception'},
        {'id': 10, 'director': 'Christopher Nolan', 'title': 'Batman Begins'}
      ],
      searchQuery: ''
    }
  },
  computed: {
    filteredMovies () {
      const query = this.searchQuery.toLowerCase()
      return this.movies.filter(
        (movie) =>
          movie.title.toLowerCase().includes(query) ||
          movie.director.toLowerCase().includes(query)
      )
    }
  }
}
</script>

<style>
.movies {
  display: flex;
  flex-wrap: wrap;
  align-content: center;
}
.app{
  background-color: aqua;
  align-content: center;
  text-align: center; /* Center the text horizontally */
  /*max-width: 600px; /* Adjust this value as needed */
  /*padding: 20px;*/
}
</style>
