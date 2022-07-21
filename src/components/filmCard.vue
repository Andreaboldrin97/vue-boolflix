<template>
    <div>
        <ul>
            <li>{{ filmTitle }}</li>
            <li> {{ originalTitleFilm }}</li>
            <li>{{ originalLanguageFilm }}</li>
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
    }
}
</script>

<style lang="scss">

</style>