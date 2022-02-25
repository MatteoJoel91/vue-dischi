<template>
    <div class="header-top d-flex justify-content-between align-items-center">
        <img src="../assets/img/logo.svg" alt="">
        <div class="ms_select">
      <select v-model="selectedGenre" @change="$emit('selectedGenreEvt', selectedGenre)">
         <option value="">Seleziona il genere</option>
         <option v-for="(genre, index) in genresList" :value="genre" :key="index">{{genre}}</option> 
      </select> 
  </div>
    </div>
    
</template>

<script>


export default {
    name: 'MyHeader',
    
    props: {
        'genresList': Array
        },
    data(){
        return{
            selectedGenre: '',
        }
    }
}
    
</script>

<style scoped lang="scss">
    .header-top{
        width: 100%;
        height: 50px;
        background-color: #2e3a46;

        img{
            width: 120px;
            margin-left: 10px;
        }
    }
    .ms_select{
        margin-right: 10px;
    }
</style>