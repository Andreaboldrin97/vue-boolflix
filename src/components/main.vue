<template>
    <div>
        <div>
            <h4>FILM</h4>
             <filmCard v-for="(element , index) in filmContent" :key="index"
            :filmTitle="element.title"
            :originalTitle="element.original_title"
            :originalLanguageFilm="element.original_language"
            :filmVote="element.vote_average"
            />
        </div>
       <div>
           <h4>SERIE TV</h4>
           <serieCard v-for="(series, index ) in seriesTVContent" :key="index"
            :serieTitle="series.name"
            :serieOriginalTitle="series.original_name"
            :serieOriginalLanguage="series.original_language"
            :serieVote="series.vote_average"
            />
       </div>
        
    </div>
</template>

<script>
import filmCard from './filmCard.vue' 
import serieCard from './serieCard.vue' 

export default {
    components :{
        filmCard,
        serieCard
    },
    props:{
        filmContent : Array,
       seriesTVContent : Array,
    },
   
}
</script>

<style lang="scss">

</style>