<template>
    <div>
        <ul>
            <li>{{ filmTitle }}</li>
            <li> {{ originalTitleFilm }}</li>
            <li class="img-language"><img :src="require(`../assets/flag-${visualLanguage(originalLanguageFilm)}`)" alt=""></li>
            <li>{{ filmVote }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    
    props : {
        filmTitle : String,
        originalTitleFilm : String,
        originalLanguageFilm : String,
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