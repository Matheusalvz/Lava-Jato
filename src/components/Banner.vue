<template>
<div id="main-banner">
    <h1>Lava Car</h1>
</div>
   
</template>

<script>
export default{
    name: "Banner"
}
</script>


<style scoped>
    #main-banner{
        background-image: url('/home/matheus/Documentos/Projetos/lava_jato/public/img/banner.jpg');
        background-position: 0 -250px;
        /* background-size: cover; */
        height: 500px;
        display: flex;
        align-items: center;
        justify-content: flex-start;
    }

    #main-banner h1{
        color: #FFF;
        text-align: center;
        font-size: 60px;
        background-color: #222;
        padding: 15px 30px;
    }
</style>