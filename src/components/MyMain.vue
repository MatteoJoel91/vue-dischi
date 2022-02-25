<template>
    <div class="container">

        <div class="row row-cols-2 row-cols-sm-3 row-cols-lg-5 justify-content-center ">

            <AlbumSingolo
            v-for="(album, indice) in filteredAlbum" 
            :key="indice"
            :album="album"
            >
            </AlbumSingolo>

        </div>
</div>
</template>

<script>

    // integro axios
    const axios = require('axios');
    import AlbumSingolo from './partials/AlbumSingolo.vue'

export default {
    name: 'MyMain',
    props: {
        'selectedGenre' :String,
        },
    data(){
        return{
            listaAlbum: [],
            listaGeneri: [],
        }
    },
    components:{
        AlbumSingolo,
    },
    computed:{
        filteredAlbum(){
            if(this.selectedGenre == ''){
                return this.listaAlbum;
            }else{
               return this.listaAlbum.filter(element =>{
                return element.genre == this.selectedGenre;
                }); 
            }
            
            
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

                for (let i = 0; i < this.listaAlbum.length; i++) {
                    if(!this.listaGeneri.includes(response.data.response[i].genre)){
                        this.listaGeneri.push(response.data.response[i].genre);    
                    } 
                }
                console.log(this.listaGeneri);
                this.$emit("genresReady", this.listaGeneri);
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
    
</style>