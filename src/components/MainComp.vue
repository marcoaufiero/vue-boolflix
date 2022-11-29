<template>
    <main>
        <MoviesBox :movies="movies"/>
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

</style>