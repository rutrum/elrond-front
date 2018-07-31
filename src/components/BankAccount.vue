<template>
    <div id="bankaccount">
        <h2 id="subtitle">{{ title }}</h2>
        <div style="width: 500px" class="small-form">
            <!-- If this dosen't work from you, you need the plaid QuickStart demo. git clone https://github.com/plaid/quickstart.git  -->
            <iframe style="width: 470px; height: 500px" src="http://localhost:8000"></iframe>
            <button id="back" @click="$emit('changepage','overview')">Back to Overview</button>
        </div>
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
        },
        beforeMount() {
            const stripe = stripePackage("sk_test_1bYR86tBWv609YNATBbdnIog");

            // Token is created using Checkout or Elements!
            // Get the payment token ID submitted by the form:
            //const token = request.body.stripeToken; // Using Express
            const token = "tok_1Cu6Q3L3Fu2e0RuvCOwLT8WW";

            const charge = stripe.charges.create({
            amount: 60,
            currency: 'usd',
            description: 'Example charge',
            source: token,
            });
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
