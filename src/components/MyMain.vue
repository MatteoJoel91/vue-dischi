<template>
    <div class="container">
  <div class="row row-cols-2 row-cols-sm-3 row-cols-lg-5 justify-content-center">

    <div class="text-center" v-for="(album, indice) in listaAlbum" :key="indice">
        <div class="ms_box">
            <img class="ms_img-fluid" :src="album.poster" alt="">
            <h3>{{album.title}}</h3>
            <h5>{{album.author}}</h5>
            <h5>{{album.year}}</h5>
        </div>
      
    </div>

  </div>
</div>
</template>

<script>

    // integro axios
    const axios = require('axios');

export default {
    name: 'MyMain',
    data(){
        return{
            listaAlbum: []
        }
    },
    methods:{
        getAlbum(){
            // Make a request for a user with a given ID
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                // handle success
                this.listaAlbum = response.data.response;
                console.log(response);
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .then(function () {
                // always executed
            });
        }
    },
    created(){
        this.getAlbum();
    }
}
</script>

<style scoped lang="scss">
    .ms_img-fluid{
        margin: 10px 0px;
        width: 90%;
}

    .ms_box{
        width: 200px;
        min-height: 380px;
        background-color: #2e3a46;
        margin: 30px;
        padding: 5px;
    }
</style>