<template>
  <div id="app">
    <headerContent @search="searchPoster" @isNavOpen="openNav"/>
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
          apiKey : '3b41601b192f01bf36adb6163387f7eb',
          apiLink : 'https://api.themoviedb.org/3/search/',
          titleSearch : '',
          filmContent : [],
          seriesTVContent : [],
          navIsOpen : false
          

      }
  },
  methods : {
       getFilm : function(){

            axios.get(this.apiLink + 'movie', {params: {api_key : this.apiKey, query: this.titleSearch}})
            .then((element) =>{
              this.filmContent = element.data.results
            
            })
            .catch((error) => {
              console.warn(error)
            })
       },
       getSerie : function(){
          const parameters= {
           api_key : this.apiKey,
           query: this.titleSearch
         }
            axios.get(this.apiLink + 'tv',{params:parameters})
            .then((element) =>{
              this.seriesTVContent = element.data.results
            
            })
            .catch((error) => {
              console.warn(error)
            })
       },
       searchPoster : function(needle){
         console.log(needle)
         this.titleSearch = needle;
         this.getFilm();
         this.getSerie()
         
       },
       openNav : function(needle){
         return this.navIsOpen = needle
       }
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&family=Roboto:wght@100;400;500;700&display=swap');
body{
  font-family: 'Roboto', sans-serif;
}

//? usato la cdn per problemi nel verificamento delle icon
// @import "~font-awesome/css/font-awesome.css";

</style>
