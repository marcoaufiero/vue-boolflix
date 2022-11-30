<template>
    <main>
        <h1>Movies</h1>
        <MoviesBox :movies="movies"/>
        <h1>TV Series</h1>
        <SeriesBox :series="series"/>
    </main>
</template>

<script>
import MoviesBox from './MoviesBox.vue'
import SeriesBox from './SeriesBox.vue'

    export default {
        name: 'MainComp',
        props: {
            movies: Array,
            series: Array
        },
        components: {
            MoviesBox,
            SeriesBox
        }
    }
</script>

<style lang="scss" scoped>
    main{
        
        h1{
            color: white;
            font-size: 3rem;
            text-align: center;
            margin: 30px 0;
        }
    }
</style>