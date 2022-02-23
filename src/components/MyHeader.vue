<template>
    <div class="header-top d-flex ">
        <img src="../assets/img/logo.svg" alt="">
    </div>
</template>

<script>
export default {
    name: 'MyHeader',
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
</style>