<template>
    <main class="container-fluid px-5 py-3 container-posters" @mouseover="$emit('isNavOpen' , false)">
        <div>
            <h4 class="text-white py-3" v-if="filmContent.length > 0">LISTA DEI FILM</h4>
            <h4 v-else> Non sono stati trovati film</h4>
            <div class="row row-cols-3 row-cols-lg-5">
                <cardElement v-for="element in filmContent" :key="element.id"
                    :cardPoster="element.poster_path"
                    :cardTitle="element.title"
                    :originalTitle="element.original_title"
                    :originalLanguage="element.original_language"
                    :cardVote="element.vote_average"
                    :storyline="element.overview"
                    />
            </div>
        </div>
       <div>
           <h4 class="text-white py-3" v-if="seriesTVContent.length > 0">LISTA DELLE SERIE TV</h4>
           <h4 v-else> Non sono state trovate serie TV</h4>
           <div class="row row-cols-3 row-cols-lg-5 ">
                <cardElement v-for="series in seriesTVContent" :key="series.id"
                    :cardPoster="series.poster_path"
                    :cardTitle="series.name"
                    :originalTitle="series.original_name"
                    :originalLanguage="series.original_language"
                    :cardVote="series.vote_average"
                    :storyline="series.overview"
                    />
           </div>
       </div>
        
    </main>
</template>

<script>
import cardElement from './cardElement.vue' 

export default {
    components :{
        cardElement,
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