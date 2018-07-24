<template>
    <div id="app">
        <Main></Main>
    </div>
</template>

<script>
    import Main from './components/Main.vue'
    //import './plugins/vuetify.js';

    export default {
        name: 'app',
        components: {
            Main
        }
    }
</script>

<style>
    * {
        padding: 0;
        margin: 0;
    }
</style>