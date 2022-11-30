<template>
    <div class="card">
        <div>
            <img class="poster" :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="">
            <div class="info">
                <h2>{{serie.name}}</h2>
                <h4>Lingua: {{serie.original_language.toUpperCase()}}</h4>
                <h4>Voto: {{serie.vote_average}}</h4>
                <img :src="`https://www.countryflagicons.com/SHINY/32/${serie.original_language.toUpperCase()}.png`">
                <font-awesome-icon v-for="(fullstar, index) in this.serie.vote_average" :key="index" icon="fa-solid fa-star" />
                <font-awesome-icon v-for="(emptystar, index) in 5 - this.serie.vote_average" :key="index+9999" icon="fa-regular fa-star" />
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
        
        beforeUpdate(){
            this.displayRating(this.serie)

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
            },

            displayRating(elem){
                let vote = parseInt(Math.round(elem.vote_average)/2);
                elem.vote_average = vote;
            },
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
        }

    }

</style>