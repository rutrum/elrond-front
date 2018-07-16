<template>
    <div id="main">
        <h1>{{ title }}</h1>
    </div>
</template>

<script>
    export default {
        name: 'main',
        data() {
            return {
                title: "Project Elrond"
            }
        }
    }
</script>

<style>
    h1 {
        text-align: center;
        font-size: 40px;
    }
</style>