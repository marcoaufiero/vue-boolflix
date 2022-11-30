<template>
    <div class="card">
        <div>
            <img class="poster" :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="">
            <div class="info">
                <h3>Titolo: {{serie.name}}</h3>
                <h4>Lingua: {{serie.original_language.toUpperCase()}}</h4>
                <h4>Voto: {{serie.vote_average}}</h4>
                <img :src="`https://www.countryflagicons.com/SHINY/32/${serie.original_language.toUpperCase()}.png`">
            </div>
            
        </div>
    </div>
</template>

<script>
    export default {
        name: 'SerieCard',
        props:{
            serie: Object
        },

        mounted(){
            this.flagFix(this.serie)
        },
        
        methods:{
            flagFix(obj){
                if(obj.original_language == 'en'){
                    obj.original_language = 'us'
                }else if(obj.original_language == 'ja'){
                    obj.original_language = 'jp'
                }else if(obj.original_language == 'uk'){
                    obj.original_language = 'gb'
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    
    .card{
        
        background-color: black;
        aspect-ratio: 2/3;
        height: 30vh;
        color: white;
        padding: 10px;
        margin: 0 10px;
        border-radius: 10px;

        &:hover{
            cursor: pointer;

            .poster{
                display: none;
            }

            .info{
                display: block;
            }
        }

        .poster{
            z-index: 2;
            width: 100%;
        }

        .info{
            display: none;

            *{
                padding: 10px 20px;
            }
        }

    }

</style>