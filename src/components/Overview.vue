<template>
    <div id="overview">
        <h2 id="subtitle">{{ title }}</h2>
        <div class="big-form">
            <button @click="$emit('changepage','transactions')">View your transactions.</button>
            <button @click="$emit('changepage','preferences')">Change preferences.</button>
            <button @click="$emit('changepage','bankaccount')">Edit bank information.</button>
            <br>
            <button @click="$emit('changepage','loginregister')">Logout</button>
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