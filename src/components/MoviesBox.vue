<template>
    <div>
        <CardComp v-for="(elem,index) in movies" :key="index" :movie="elem"/>
    </div>
</template>

<script>
import CardComp from './MovieCard.vue'

    export default {
        name: 'MoviesBox',
        props: {
            movies: Array,
        },
        components: {
            CardComp
        }
    }
</script>

<style lang="scss" scoped>

</style>