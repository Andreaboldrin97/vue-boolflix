<template>
    <section class="p-1 " :class="cardPoster == null ? 'd-none' : 'd-block'">
            <div class="position-relative card-container">
                <img class="img-path" :src="`https://image.tmdb.org/t/p/w342${cardPoster}`" :alt="`path-${cardTitle}`">
                <div class="position-absolute top-0 card-info p-3">
                    <div :class="cardTitle == null ? 'd-none' : 'd-block'">
                         Titolo :{{ cardTitle }}
                    </div>
                    <div :class="originalTitle == null ? 'd-none' : 'd-block'"> 
                        Titolo originale :{{ originalTitle }}
                    </div>
                    <div class="img-language" :class="originalLanguage== null ? 'd-none' : 'd-block'">
                        Lingua originale :<img :src="require(`../assets/flag-${visualLanguage(originalLanguage)}`)" alt="">
                    </div>
                    <div :class="cardVote == 0 ? 'd-none' : 'd-block'">
                        Voto :  
                        <i v-for="n in 5" :key="n" class="far fa-star text-warning" :class=" n <= rating(cardVote) ? 'fas' : 'far' "></i>
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
        cardTitle : String,
        originalTitle : String,
        originalLanguage: String,
        cardPoster : String,
        storyline : String,
        cardVote : [String,Number],
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
            // let star = '⭐'
            // let ratings= Math.ceil( vote / 2) 
            // const stars = star.repeat(ratings)
            // return stars 
            return Math.ceil( vote / 2)
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
    min-height: 400px;
    object-fit: cover;
}
.card-container{
    transform: 1s;
}
.card-info{
    width: 100%;
    height: 100%;
    font-size: 8px;
    display: none;
}
.card-container:hover .card-info{
    display: block;
    background-color: black;
    color: white;
    border: 2px solid red;
    border-radius: 20px;
   transform: scale(1.2);
   z-index: 2;
}


</style>