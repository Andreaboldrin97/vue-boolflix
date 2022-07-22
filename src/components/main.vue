<template>
    <main class="container-fluid px-5 py-3 container-posters" @mouseover="$emit('isNavOpen' , false)">
        <div>
            <h4 class="text-white py-3" v-if="filmContent != '' ? 'd-block' : ''">LISTA DEI FILM</h4>
            <div class="row row-cols-5 ">
                <cardElement v-for="(element , index) in filmContent" :key="index"
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
           <h4 class="text-white py-3" v-if="seriesTVContent != '' ? 'd-block' : ''">LISTA DELLE SERIE TV</h4>
           <div class="row row-cols-5">
                <cardElement v-for="(series, index ) in seriesTVContent" :key="index"
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