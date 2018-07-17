<template>
    <div id="login">
        <h2 id="subtitle">{{ title }}</h2>
        <form id="login-form">
            <label>Username:</label><input type="text"></input><br>
            <label>Password:</label><input type="password"></input>
            <input id='submit' type="submit">
        </form>
    </div>
</template>

<script>
    export default {
        name: 'login',
        data() {
            return {
                title: "Login"
            }
        }
    }
</script>

<style>
    label {
        display: inline-block;
        width: 30%;
    }
    input {
        width: 65%;
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