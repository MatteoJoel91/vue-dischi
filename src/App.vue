<template>
  <div id="app">
    <MyHeader 
    @selectedGenreEvt="setSelectedGenre" :genresList="genresList"
    ></MyHeader>
    
    <MyMain 
    @genresReady="setGenres" :selectedGenre="selectedGenre"
    ></MyMain>
    
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain,
  },
  data(){
    return{
      genresList: [],
      selectedGenre:'',
    }
  },
  methods: {
    setGenres(genresListEvt){
      this.genresList = genresListEvt;
    },
    setSelectedGenre(selectedGenreEvt){
      this.selectedGenre = selectedGenreEvt;
    }
  }
}
</script>

<style lang="scss">
  @import "./assets/style/generale.scss";
  @import "./assets/style/variabili.scss";
</style>
