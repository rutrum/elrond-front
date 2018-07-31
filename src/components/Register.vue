<template>
    <div id="register">
        <h2 id="subtitle">{{ title }}</h2>
        <div class="big-form">
            <label>Email:</label>
            <input type="text" v-model="input.username">
            <br>
            <label>Password:</label>
            <input type="password" v-model="input.password">
            <button class="submit" type="button" v-on:click="login()">Create Account</button>
            <p class="warning">{{ output }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'register',
        data() {
            return {
                title: "Register",
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
                    //TODO ajax?
                    this.$emit("changepage","createaccount")
                } else {
                    this.output = "You need to enter a username and password.";
                }
            }
        }
    }
</script>