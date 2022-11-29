<template>
    <main>
        <MoviesBox/>
        <SeriesBox/>
    </main>
</template>

<script>
import MoviesBox from './MoviesBox.vue'
import SeriesBox from './SeriesBox.vue'

    export default {
        name: 'MainComp',
        components: {
            MoviesBox,
            SeriesBox
        }
    }
</script>

<style lang="scss" scoped>

</style>