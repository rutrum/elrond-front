<template>
    <div id="login">
        <h2 id="subtitle">{{ title }}</h2>
        <form class="big-form">
            <label>Username:</label>
            <input type="text" v-model="input.username">
            <br>
            <label>Password:</label>
            <input type="password" v-model="input.password">
            <button class="submit" type="button" @click="login()">Login</button>
            <p class="warning">{{ output }}</p>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'login',
        data() {
            return {
                title: "Login",
                input: {
                    username: "",
                    password: ""
                },
                output: ""
            }
        },
        methods: {
            login() {
                if (this.input.username != "" && this.input.password != "") {
                    this.output = ""
                    // logic
                    this.$emit("changepage", "overview")
                } else {
                    this.output = "You need to enter a username and password.";
                }
            }
        }
    }
</script>