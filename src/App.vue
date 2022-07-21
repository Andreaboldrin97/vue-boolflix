<template>
  <div id="app">
    <headerContent @search="titleFilmSearch"/>
    <mainContent />
  </div>
</template>

<script>
import headerContent from './components/header.vue'
import mainContent from './components/main.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    headerContent,
    mainContent,
  },
  data : function(){
      return{
          apiKey : '?api_key=3b41601b192f01bf36adb6163387f7eb',
          apiLink : 'https://api.themoviedb.org/3/search/',
          movie : 'movie',
          titleSearch : '',
          filmTitle : [] ,
          originalTitleFilm : [],
          originalLanguageFilm : []

      }
  },
  methods : {
       getFilm : function(){
            axios.get(`${this.apiLink}${this.movie}${this.apiKey}${this.titleSearch}`)
            .then((element) =>{
              this.filmsTitle = element.data.results.title;
              this.originalTitleFilm = element.data.results.original_title;
              this.originalLanguageFilm = element.data.results.original_language;
              console.log(`${this.filmsTitle} ...... ${this.originalTitleFilm} .....${this.originalLanguageFilm}`)
            })
       },
       titleFilmSearch : function(needle){
         console.log(needle)
         this.titleSearch = `&query=${needle}`;
         this.getFilm()
         console.log(`${this.apiLink}${this.movie}${this.apiKey}${this.titleSearch}`)
       }
  },
  created(){
    this.titleFilmSearch()
  }
}
</script>

<style lang="scss">
@import "~/node_modules/bootstrap/scss/bootstrap.scss";

</style>
