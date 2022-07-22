<template>
    <section class="p-3" :class="filmPoster == null ? 'd-none' : 'd-block'">
            <div class="position-relative card-container">
                <img class="img-path" :src="`https://image.tmdb.org/t/p/w342${filmPoster}`" :alt="`path-${filmTitle}`">
                <div class="position-absolute top-0 card-info p-3">
                    <div :class="filmTitle == null ? 'd-none' : 'd-block'">
                         Titolo :{{ filmTitle }}
                    </div>
                    <div :class="originalTitleFilm == null ? 'd-none' : 'd-block'"> 
                        Titolo originale :{{ originalTitleFilm }}
                    </div>
                    <div class="img-language" :class="originalLanguageFilm == null ? 'd-none' : 'd-block'">
                        Lingua originale :<img :src="require(`../assets/flag-${visualLanguage(originalLanguageFilm)}`)" alt="">
                    </div>
                    <div :class="filmVote == 0 ? 'd-none' : 'd-block'">
                        Voto : {{ rating(filmVote) }}
                    </div>
                    <div :class="storyline == '' ? 'd-none' : 'd-block'">
                        Trama : {{ storyline }}
                    </div>
                </div>
            </div>
    </section>
</template>

<script>
export default {
    
    props : {
        filmTitle : String,
        originalTitleFilm : String,
        originalLanguageFilm : String,
        filmPoster : String,
        storyline : String,
        filmVote : [String,Number],
    },
     data : function(){
        return{
            filmLanguage : [ 'it' , 'en' , 'es' ,'fr']
        }
    },
    methods : {
        visualLanguage : function(langauge){
            if(this.filmLanguage.includes(langauge)){
                return `${langauge}.png`
            }else{
                return langauge
            }
        },
            rating : function(vote){
            let star = '⭐'
            let ratings= Math.round( vote / 2) 
            const stars = star.repeat(ratings)
            return stars
        }
    }
}
</script>

<style lang="scss" scoped>
.img-language{
   img{
       width: 20px;
       object-fit: cover;
       object-position: center;
   }
}
.img-path{
    width: 100%;
    height: 400px;
    object-fit: cover;
}
.card-info{
    width: 100%;
    height: 100%;
    font-size: 12px;
    display: none;
}
.card-container:hover .card-info{
    display: block;
    background-color: black;
    color: white;
}


</style>