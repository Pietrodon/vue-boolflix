<template>
    <div id="app">
        <div>
            <input type="text" placeholder="Cerca Film" v-model="search">
            <button>Cerca</button>
        </div>        
        <div v-for="movie in movies" :key="movie.id">
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
          search:'ritorno',
          movies:[],   
      }   
  },
  created(){

      axios.get('https://api.themoviedb.org/3/search/movie/?api_key=d6d1e144bc9bbed54e5110613577c788&query=batman')
      .then(res =>{
          console.log(res.data)
          this.movies = res.data.results
      })

  } 

}
</script>



<style scoped lang="scss">

</style>

