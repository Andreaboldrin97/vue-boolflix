<template>
    <div>
        <ul>
            <li>{{  serieTitle }}</li>
            <li>{{serieOriginalTitle}}</li>
            <li class="img-language"><img :src="require(`../assets/flag-${visualLanguage(serieOriginalLanguage)}`)" alt=""></li>
            <li>{{ serieVote }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    
    props : {
        serieTitle : String,
        serieOriginalTitle : String,
        serieOriginalLanguage: String,
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
        }
    }
}
</script>

<style lang="scss" scoped>
.img-language{
   img{
       width: 20px;
       height: 20px;
   }
}

</style>