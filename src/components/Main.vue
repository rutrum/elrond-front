<template>
    <div id="main">
        <h1 id="title">{{ title }}</h1>
        <Login></Login>
    </div>
</template>

<script>
    import Login from './Login.vue'
    
    export default {
        name: 'main',
        components: {
            Login
        },
        data() {
            return {
                title: "Project Elrond"
            }
        }
    }
</script>

<style>
    #title {
        text-align: center;
        padding: 20px;
        background-color: rgb(170, 202, 107);
    }
    #subtitle {
        text-align: center;
        padding: 10px;
        background-color: rgb(197, 236, 111);
    }
</style>