<template>
    <div id="elrond">
        <h1 id="title">{{ title }}</h1>
        <div id="pagecontent">
            <div v-if="page === 'loginregister'" id="loginpage">
                <Login @changepage="page=$event"></Login>
                <Register @changepage="page=$event"></Register>
            </div>
            <Overview       v-if="page === 'overview'"      @changepage="page=$event"></Overview>
            <CreateAccount  v-if="page === 'createaccount'" @changepage="page=$event"></CreateAccount>
            <Preferences    v-if="page === 'preferences'"   @changepage="page=$event"></Preferences>
            <BankAccount    v-if="page === 'bankaccount'"   @changepage="page=$event"></BankAccount>
            <Transactions   v-if="page === 'transactions'"  @changepage="page=$event"></Transactions>
        </div>
    </div>
</template>

<script>
    import Login from './Login.vue'
    import Register from './Register.vue'
    import CreateAccount from './CreateAccount.vue'
    import Preferences from './Preferences.vue'
    import BankAccount from './BankAccount.vue'
    import Transactions from './Transactions.vue'
    import Overview from './Overview.vue'

    export default {
        name: 'elrond',
        components: {
            Login,
            CreateAccount,
            Register,
            Preferences,
            BankAccount,
            Transactions,
            Overview
        },
        data() {
            return {
                title: "Project Elrond",
                page: "loginregister"
            }
        }
    }
</script>

<style>
    body {
        background: linear-gradient(to right, white, darkgrey, darkgrey, darkgrey, white);
    }
    #pagecontent {
        background-color: white;
        width: 60%;
        margin: 50px auto;
    }
    #loginpage {
        display: flex;
        justify-content: center;
    }
    #loginpage > div{
        width: 50%;
    }
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
    button {
        margin: 20px auto 5px auto;
        width: 70%;
        display: block;
    }
    .big-form {
        margin: 70px auto;
        width: 60%;
        border: solid black 1px;
        padding: 10px;
        background-color: #F8F9F9;
    }
    .small-form {
        margin: 70px auto;
        width: 30%;
        border: solid black 1px;
        padding: 10px;
        background-color: #F8F9F9;
    }
    @media only screen and (max-width: 1200px) {
        #pagecontent {
            width: 100%;
        }
    }
</style>