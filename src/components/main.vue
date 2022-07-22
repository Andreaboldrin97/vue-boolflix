<template>
    <div class="container-fluid">
        <div >
            <h4>FILM</h4>
            <div class="row row-cols-6 justify-content-center">
                <filmCard v-for="(element , index) in filmContent" :key="index"
                    :filmPoster="element.poster_path"
                    :filmTitle="element.title"
                    :originalTitle="element.original_title"
                    :originalLanguageFilm="element.original_language"
                    :filmVote="element.vote_average"
                    />
            </div>
        </div>
       <div>
           <h4>SERIE TV</h4>
           <div class="row row-cols-6 justify-content-center">
                <serieCard v-for="(series, index ) in seriesTVContent" :key="index"
                    :posterPath="series.poster_path"
                    :serieTitle="series.name"
                    :serieOriginalTitle="series.original_name"
                    :serieOriginalLanguage="series.original_language"
                    :serieVote="series.vote_average"
                    />
           </div>
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