<template>
    <div id="bankaccount">
        <h2 id="subtitle">{{ title }}</h2>
        <form class="small-form">
            <div>
                <label>Bank name:</label>
                <input type="text" v-model="input.bankname">
            </div>
            <div>
                <label>Routing Number:</label>
                <input type="num" v-model="input.routingnumber">
            </div>
            <div>
                <label>Checking Number:</label>
                <input type="num" v-model="input.checkingnumber">
            </div>
            <button type="button" v-on:click="save()">Save</button>
            <p class="warning">{{ output }}</p>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'BankAccount',
        data() {
            return {
                title: "Bank Account Information",
                input: {
                    bankname: "",
                    routingnumber: "",
                    checkingnumber: ""
                },
                output: ""
            }
        },
        methods: {
            save() {
                // Save options
                this.output = "Information saved."
            }
        }
    }
</script>

<style>

    #roundingoptions {
        display: flex;
        align-items: center;
        align-content: center;
    }
    #roundingoptions > div {
        width: 100%;
    }
    #roundingoptions input {
        margin: 2px;
        width: initial;
    }
    #roundingoptions label {
        margin: 2px;
        display: inline;
    }
    .login-form > input{
        width: 100px;
    }
</style>
