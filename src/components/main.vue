<template>
    <div>
        <filmList v-for="(element , index) in filmContent" :key="index"
        :filmTitle="element.title"
        :originalTitleFilm="element.original_title"
        :originalLanguageFilm="element.original_language"
        :filmVote="element.vote_average"
        />
    </div>
</template>

<script>
import filmList from './filmCard.vue' 

export default {
    components :{
        filmList
    },
    props:{
        filmContent : Array,
    },
   
}
</script>

<style lang="scss">

</style>s