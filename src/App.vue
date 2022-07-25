<template>
  <div id="app">
    <headerContent @search="titleSearch" @isNavOpen="openNav"/>
    <div class="d-flex">
    <userBar :navIsOpen="navIsOpen"/>
    <mainContent @isNavOpen="openNav"
      :filmContent="filmContent"
      :seriesTVContent="seriesTVContent"
    />
    </div>
  </div>
</template>

<script>
import headerContent from './components/header.vue'
import mainContent from './components/main.vue'
import userBar from './components/userBar.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    headerContent,
    mainContent,
    userBar
  },
  data : function(){
      return{
          apiKey : '?api_key=3b41601b192f01bf36adb6163387f7eb',
          apiLink : 'https://api.themoviedb.org/3/search/',
          movie : 'movie',
          seriesTv : 'tv',
          titleSearch : '',
          filmContent : [],
          seriesTVContent : [],
          navIsOpen : false
          

      }
  },
  methods : {
       getFilm : function(){
            axios.get(`${this.apiLink}${this.movie}${this.apiKey}${this.titleSearch}`)
            .then((element) =>{
              this.filmContent = element.data.results
            
            })
            .catch((error) => {
              console.warn(error)
            })
       },
       getSerie : function(){
            axios.get(`${this.apiLink}${this.seriesTv}${this.apiKey}${this.titleSearch}`)
            .then((element) =>{
              this.seriesTVContent = element.data.results
            
            })
            .catch((error) => {
              console.warn(error)
            })
       },
       titleSearch : function(needle){
         console.log(needle)
         this.titleSearch = `&query=${needle}`;
         this.getFilm();
         this.getSerie()
         console.log(`${this.apiLink}${this.seriesTv}${this.apiKey}${this.titleSearch}`)
       },
       openNav : function(needle){
         return this.navIsOpen = needle
       }
  }
}
</script>

<style lang="scss">
@import "~/node_modules/bootstrap/scss/bootstrap.scss";
@import "~/node_modules/font-awesome/scss/font-awesome.scss";

</style>
