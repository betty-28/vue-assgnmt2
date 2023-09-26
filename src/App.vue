<template>
  <div id="app">
    <h1>Movie Information</h1>
    <input v-model="searchQuery" placeholder="Search by name or director" />
    <div class="movies">
      <Movie
        v-for="movie in filteredMovies"
        :key="movie.id"
        :movie="movie"
      />
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue' // Import the Movie component

export default {
  components: {
    HelloWorld
  },
  data () {
    return {
      movies: [{'id':1,'director':'1','title':'Titanic'},
{'id':2,'director':'1','title':'The Terminator'},
{'id':3,'director':'1','title':'Avatar'},
{'id':4,'director':'2','title':'Baahubali'},
{'id':5,'director':'2','title':'RRR'},
{'id':6,'director':'2','title':'Avatar'},
{'id':7,'director':'3','title':'Guardians Of Galaxy'},
{'id':8,'director':'4','title':'The Dark Knight'},
{'id':9,'director':'4','title':'Inception'},
{'id':10,'director':'4','title':'Batman Begins'}],
      searchQuery: ''
    }
  },
  computed: {
    filteredMovies () {
      const query = this.searchQuery.toLowerCase()
      return this.movies.filter(
        (movie) =>
          movie.name.toLowerCase().includes(query) ||
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
}
</style>
