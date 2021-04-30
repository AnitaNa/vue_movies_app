<template>
  <div>
    <h3>Movies Names</h3>
     <p>{{movies}}</p>
      <p>{{movies.Title}}</p>
     <input type="text" v-model="search" placeholder="Enter name here...">
      <!-- <div v-for="movie in movies" :key="movie" > -->
        <ul >
          <li v-for="(movie, index) in movies" :key="index">{{movie.Year}} !!</li>
        </ul>
        <h1></h1>
        
      <!-- </div>   -->
   
</div>
</template>

<script>


 //const API = 'http://www.omdbapi.com/?i=tt3896198&apikey=21ce1676'
export default {
  data(){
    return {
      movies: [],
      search: ''

    }
  },

   mounted(){
     fetch('http://www.omdbapi.com/?i=tt3896198&apikey=21ce1676')
     .then(res => res.json())
     .then(data => this.movies = data)
     .catch(err => console.log(err.message) )
  },

  computed: {
    fiteredMovie: function(){
      return this.movies.filter(movie => {
        return movie.body.toLowerCase().includes(this.search.toLowerCase())
      })
    }

    
  }
  // methods: {
  //      async fetchApi(){
  //       await axios.get('http://www.omdbapi.com/?i=tt3896198&apikey=21ce1676')
  //       .then(res => res.json()
  //       .then(data => this.responseData = data.data)
  //       .catch( err => console.log(err))
  //     }
  // },


}

</script>

<style>

</style>


 
   