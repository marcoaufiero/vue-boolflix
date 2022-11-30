<template>
    <div class="card">
        <div>
            <img class="poster" :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="">
            <div class="info">
                <h2>{{serie.name}}</h2>
                <h4>Lingua: {{serie.original_language.toUpperCase()}}</h4>
                <div>
                    Voto: 
                    <font-awesome-icon v-for="(fullstar, index) in displayRating(this.serie)" :key="index" icon="fa-solid fa-star" />
                    <font-awesome-icon v-for="(emptystar, index) in 5 - displayRating(this.serie)" :key="index+9999" icon="fa-regular fa-star" />
                </div>
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
            },

            displayRating(elem){
                let vote = Math.round(elem.vote_average/2);
                return vote;
            },
        }
    }
</script>

<style lang="scss" scoped>
    
    .card{
        
        background-color: black;
        aspect-ratio: 2/3;
        height: 32vh;
        color: white;
        padding: 5px;
        margin: 0 10px;
        border-radius: 15px;

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
            border-radius: 10px;
        }

        .info{
            display: none;
            padding: 10px;

            h2{
                color: #8a0a0a;
            }

            > *{
                margin-bottom: 10px;
            }

            .fa-star{
                color: yellow;
            }
        }

    }

</style>