<template>
    <div id="main">
        <h1 id="title">{{ title }}</h1>
        <Login style="width: 50%; display: inline-block"></Login>
        <Register style="width: 50%; display: inline-block"></Register>
        <CreateAccount></CreateAccount>
    </div>
</template>

<script>
    import Login from './Login.vue'
    import Register from './Register.vue'
    import CreateAccount from './CreateAccount.vue'
    
    export default {
        name: 'main',
        components: {
            Login,
            CreateAccount,
            Register
        },
        data() {
            return {
                title: "Project Elrond",
                showlogin: false
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
    label {
        display: inline-block;
        margin: 2px;
        width: 30%;
    }
    input {
        width: 60%;
        margin: 4px;
    }
    .warning {
        margin: 2px;
        color: red;
        text-align: center;
    }
    .submit {
        margin: 30px auto 5px auto;
        width: 70%;
        display: block;
    }
    .login-form {
        margin: 100px auto;
        width: 60%;
        border: solid black 1px;
        padding: 10px;
    }
    .big-form {
        margin: 100px auto;
        width: 30%;
        border: solid black 1px;
        padding: 10px;
    }
</style>