<template>
    <div class="card">
        <div>
           <h3>Titolo: {{movie.title}}</h3>
           <h4>Titolo originale: {{movie.original_title}}</h4>
           <h4>Lingua: {{movie.original_language}}</h4>
           <h4>Voto: {{movie.vote_average}}</h4>
            <img :src="`https://www.countryflagicons.com/SHINY/32/${movie.original_language.toUpperCase()}.png`">
        </div>
    </div>
</template>

<script>
    export default {
        name: 'SerieCard',
        props:{
            movie: Object
        },
        
        mounted(){
            this.flagFix(this.movie)
        },
        
        methods:{
            flagFix(obj){
                if(obj.original_language == 'en'){
                    obj.original_language = 'us'
                }else if(obj.original_language == 'ja'){
                    obj.original_language = 'jp'
                }
            }
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