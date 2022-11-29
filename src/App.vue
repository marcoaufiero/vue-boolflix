<template>
  <div id="app">
    <HeaderComp/>
    <MainComp/>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
// import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
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
