<template>
    <div id="app">
        <div class="search-bar">
            <input type="text" placeholder="Cerca Film" v-model="search" @keyup.enter="richiamoApi">
            <button @click="richiamoApi">Cerca</button>
        </div>        
        <div v-for="movie in movies" :key="movie.id" class="movie">
            {{movie.title}}
        </div>
          
    </div>
</template>
<script>
import axios from 'axios'



export default {
  name: 'App',
  data() {
      return{
          search:'',
          movies:[],   
      }   
  },
  methods:{
      richiamoApi: function() {
      axios.get(`https://api.themoviedb.org/3/search/movie/?api_key=d6d1e144bc9bbed54e5110613577c788&query=${ this.search }`)
      .then(res =>{
          console.log(res.data)
          this.movies = res.data.results
      })
  } 
  }
}
</script>



<style scoped lang="scss">
.search-bar{
    background-color: black;
    
}
.movie{
    background: grey;
    position: flex;
    color:green
}


</style>

