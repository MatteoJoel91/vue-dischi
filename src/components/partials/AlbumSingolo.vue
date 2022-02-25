<template>
    <div class="text-center ">
        <div class="ms_box ">
            <img class="ms_img-fluid" :src="album.poster" alt="">
            <h3>{{album.title}}</h3>
            <h5>{{album.author}}</h5>
            <h5>{{album.year}}</h5>
        </div>  
    </div>
</template>

<script>
export default {
    name: 'AlbumSingolo',
    props:{
        "album": Object
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