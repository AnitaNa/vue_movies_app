<template>
  <div id="app">
   <MoviesCard/>
   <div v-for="movie in filterPost" :key="movie.id">
       <MoviesContainer :movie="movie">
         
       </MoviesContainer>
       
   </div>
   </div>
  
</template>

<script>

import MoviesContainer from './components/MoviesContainer'
import MoviesCard from './components/MoviesCard'

export default {
  name: 'App',
  components: {MoviesContainer, MoviesCard},
  data(){
     return{
      //  search: '',
      //  showMovie: false,
      //  movies: [],
       
    
     }
  },

  
  methods: {
  
  //  mounted () {
  //   axios
  //     .get(this.api_url)
  //     .then(response => response.json())
  //     .then(data => data.this.movies)
  // }

  },

  computed: {
    // filterPost() {

    //   return this.movies.filter(movie => movie.body.toLowerCase().includes(this.search.toLowerCase()))
     
    // }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>


// http://www.omdbapi.com/?apikey=21ce1676&