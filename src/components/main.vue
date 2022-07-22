<template>
    <main class="container-fluid px-5 py-3 container-posters" @mouseover="$emit('isNavOpen' , false)">
        <div>
            <h4 class="text-white py-3" v-if="filmContent != '' ? 'd-block' : ''">LISTA DEI FILM</h4>
            <div class="row row-cols-5 ">
                <filmCard v-for="(element , index) in filmContent" :key="index"
                    :filmPoster="element.poster_path"
                    :filmTitle="element.title"
                    :originalTitle="element.original_title"
                    :originalLanguageFilm="element.original_language"
                    :filmVote="element.vote_average"
                    :storyline="element.overview"
                    />
            </div>
        </div>
       <div>
           <h4 class="text-white py-3" v-if="seriesTVContent != '' ? 'd-block' : ''">LISTA DELLE SERIE TV</h4>
           <div class="row row-cols-5">
                <serieCard v-for="(series, index ) in seriesTVContent" :key="index"
                    :posterPath="series.poster_path"
                    :serieTitle="series.name"
                    :serieOriginalTitle="series.original_name"
                    :serieOriginalLanguage="series.original_language"
                    :serieVote="series.vote_average"
                    :seriesStoryline="series.overview"
                    />
           </div>
       </div>
        
    </main>
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
main{
    background-color: rgb(75, 70, 70);
}
.container-posters{
    height: calc(100vh - 88px);
    overflow: auto;
}

</style>