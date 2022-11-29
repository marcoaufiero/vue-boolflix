<template>
  <div id="app">
    <HeaderComp/>
    <MainComp/>
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
      dataApi: [],
      userSearch: 'batman',
      apiPath: {
        basePath: 'https://api.themoviedb.org/3/search/',
        moviePath: 'movie',
        tvPath: 'tv',
        apiKey: '?api_key=eb79889aac5d560eff7a8e0e1277ccf2',
      },
    } 
  },
  
  mounted(){
    axios.get(`${this.apiPath.basePath}${this.apiPath.moviePath}${this.apiPath.apiKey}&query=${this.userSearch}`)
    .then((response) =>{
    this.dataApi = response.data.results
    })
  }

}
</script>

<style lang="scss">
#app {
   
  font-family: sans-serif;
  background-color: #2c3e50;
  height: 100vh;
  
  
 
}

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

</style>
