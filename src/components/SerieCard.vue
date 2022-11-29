<template>
    <div class="card">
        <div>
           <h3>Titolo: {{serie.name}}</h3>
           <h4>Lingua: {{serie.original_language}}</h4>
           <h4>Voto: {{serie.vote_average}}</h4> 
        </div>
    </div>
</template>

<script>
    export default {
        name: 'SerieCard',
        props:{
            serie: Element
        }
    }
</script>

<style lang="scss" scoped>
    
    .card{
        background-color: black;
        width: calc(100% / 6 - 40px);
        height: 300px;
        color: white;
        padding: 10px;

        *{
            margin: 10px 0;
        }
    }

</style>