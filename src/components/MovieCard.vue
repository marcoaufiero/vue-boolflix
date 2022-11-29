<template>
    <div class="card">
        <div>
           <h3>Titolo: {{movie.title}}</h3>
           <h4>Titolo originale: {{movie.original_title}}</h4>
           <h4>Lingua: {{movie.original_language}}</h4>
           <h4>Voto: {{movie.vote_average}}</h4>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CardComp',
        props:{
            movie: Element
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