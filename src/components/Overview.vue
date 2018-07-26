<template>
    <div id="overview">
        <h2 id="subtitle">{{ title }}</h2>
        <div class="big-form">
            <button>View your transactions.</button>
            <button>Change preferences.</button>
            <button>Edit bank information.</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'overview',
        data() {
            return {
                title: "Welcome!",
                input: {
                    username: "",
                    password: ""
                },
                output: ""
            }
        },
        methods: {
        }
    }
</script>