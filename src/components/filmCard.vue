<template>
    <div>
        <ul>
            <li>{{ filmTitle }}</li>
            <li> {{ originalTitleFilm }}</li>
            <li><img :src="visualLanguage(originalLanguageFilm)" alt=""></li>
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
        filmVote : [String,Number]
    },
     data : function(){
        return{
            filmLanguage : [ 'it' , 'en' , 'es' ,'fr']
        }
    },
    methods : {
        visualLanguage : function(langauge){
            if(this.filmLanguage.includes(langauge)){
                return `../assets/flag-${langauge}.png`
            }else{
                return langauge
            }
        }
    }
}
</script>

<style lang="scss">

</style>