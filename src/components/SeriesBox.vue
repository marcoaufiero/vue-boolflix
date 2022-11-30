<template>
    <div class="box">
        <SerieCard v-for="(elem,index) in series" :key="index" :serie="elem"/>
    </div>
</template>

<script>
import SerieCard from './SerieCard.vue'

    export default {
        name: 'SeriesBox',
        props: {
            series: Array,
        },
        components: {
            SerieCard
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