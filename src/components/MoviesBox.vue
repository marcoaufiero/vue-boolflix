<template>
    <div class="box">
        <MovieCard v-for="(elem,index) in movies" :key="index" :movie="elem"/>
    </div>
</template>

<script>
import MovieCard from './MovieCard.vue'

    export default {
        name: 'MoviesBox',
        props: {
            movies: Array,
        },
        components: {
            MovieCard
        },
        data(){
            return{
                
            }
        }
    }
</script>

<style lang="scss" scoped>
    
    .box{
        display: flex;
        overflow: auto;
        padding-bottom: 10px;
    }
    
</style>