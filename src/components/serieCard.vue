<template>
    <div>
        <ul>
            <li>
                <img :src="`https://image.tmdb.org/t/p/w342${posterPath}`" alt="">
            </li>
            <li>{{  serieTitle }}</li>
            <li>{{serieOriginalTitle}}</li>
            <li class="img-language"><img :src="require(`../assets/flag-${visualLanguage(serieOriginalLanguage)}`)" :alt="serieOriginalLanguage"></li>
            <li>{{ rating(serieVote) }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    
    props : {
        serieTitle : String,
        serieOriginalTitle : String,
        serieOriginalLanguage: String,
        posterPath : String,
        serieVote : [String,Number]
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
       height: 20px;
       object-fit: cover;
       object-position: center;
   }
}

</style>