<template>
    <div id="login">
        <h2 id="subtitle">{{ title }}</h2>
        <form id="login-form">
            <label>Username:</label>
            <input type="text" v-model="input.username"></input>
            <br>
            <label>Password:</label>
            <input type="password" v-model="input.password"></input>
            <button id="submit" type="button" v-on:click="login()">Login</button>
            <p id="warning">{{ output }}</p>
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
                    //TODO ajax?
                } else {
                    this.output = "You need to enter a username and password.";
                }
            }
        }
    }
</script>

<style>
    label {
        display: inline-block;
        margin: 2px;
        width: 30%;
    }
    input {
        width: 65%;
        margin: 2px;
    }
    #warning {
        color: red;
        text-align: center;
    }
    #submit {
        margin: 10px auto 5px auto;
        width: 100%
    }
    #login-form {
        margin: 100px auto;
        width: 30%;
        border: solid black 1px;
        padding: 10px;
    }
</style>