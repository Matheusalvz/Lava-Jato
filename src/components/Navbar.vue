<template>
    <div id="nav">
        <router-link to="/" id="logo-url">
            <img :src="logo" :alt="alt" id="logo" style="width: 100px; height: 100px">
        </router-link>
        <router-link to="/">Home</router-link>
        <router-link to="/pedidos">Atendimentos</router-link>
    </div>
    <router-view/>
</template>

<script>
    export default {
        name: "Navbar",
        props: ["logo", "alt"]
    }
</script>

<style scoped>
     #nav{
        background-color: #222;
        border-bottom: 4px solid #111;
        padding: 15px 50px;
        display: flex;
        justify-content: flex-end;
        align-items: flex;
    }

    #nav #logo-url{
        margin: auto;
        margin-left: 0px;
    }

    #logo{
        width: 40px;
        height: 40px;
    }

    #nav a{
        color: #0d6edd;
        text-decoration: none;
        margin: 12px;
        transition: .5s;
    }

    #nav a:hover{
        color: #FFF;
    }
</style>