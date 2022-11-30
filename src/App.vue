<template>
  <div id="app">
    <HeaderComp @search="userSearch"/>
    <MainComp :movies="moviesList" :series="seriesList"/>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  
  data(){
    return{
      moviesList: [],
      seriesList: [],
      search: '',

      apiPath: {
        basePath: 'https://api.themoviedb.org/3/search/',
        moviePath: 'movie',
        tvPath: 'tv',
        apiKey: '?api_key=eb79889aac5d560eff7a8e0e1277ccf2',
      },
    } 
  },
  
  mounted(){
    
    axios.get('https://api.themoviedb.org/3/movie/popular?api_key=eb79889aac5d560eff7a8e0e1277ccf2&language=it')
    .then((response) =>{
    this.moviesList = response.data.results
    })

    axios.get('https://api.themoviedb.org/3/tv/popular?api_key=eb79889aac5d560eff7a8e0e1277ccf2&language=it')
    .then((response) =>{
    this.seriesList = response.data.results
    })
  },

  methods:{
      userSearch(input){
      this.search = input
      this.moviesList = []
      this.seriesList = []
      
      axios.get(`${this.apiPath.basePath}${this.apiPath.moviePath}${this.apiPath.apiKey}&query=${this.search}`)
      .then((response) =>{
      this.moviesList = response.data.results
      })
      
      axios.get(`${this.apiPath.basePath}${this.apiPath.tvPath}${this.apiPath.apiKey}&query=${this.search}`)
      .then((response) =>{
      this.seriesList = response.data.results
      })
    }

  }
 
 }

  

</script>

<style lang="scss">

#app {
   
  font-family: sans-serif;
  background-color: #141414;
  width: 100vw;
  height: 100vh;
  
  ::-webkit-scrollbar{
    height: 15px; 
  }

  ::-webkit-scrollbar-track {
  background: #202020; 
  border: 2px solid black;
  margin: 0 10px;
  border-radius: 100vmax;
  }

  ::-webkit-scrollbar-thumb{
    background: black;
    // border: 2px solid #202020;
    border-radius: 100vmax;
    
    &:hover{
      background: rgb(5, 5, 5);
      cursor: pointer;
    }
  }
  

}

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;

    
  
}


  




</style>
