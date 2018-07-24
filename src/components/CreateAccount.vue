<template>
    <div id="login">
        <h2 id="subtitle">{{ title }}</h2>
        <form class="big-form">
            <h2>User Information</h2>
            <label>First:</label>
            <input type="text" v-model="input.first">
            <br>
            <label>Last:</label>
            <input type="text" v-model="input.last">
            <br>
            <label>Address:</label>
            <input type="text" v-model="input.address">
            <br>
            <label>City:</label>
            <input type="text" v-model="input.city">
            <br>
            <div>
                <div style="float: left; width: 50%">
                    <label>State:</label>
                    <input type="text" v-model="input.state">
                </div>
                <div style="float: right; width: 50%">
                    <label>Postal:</label>
                    <input type="text" v-model="input.postal">
                </div>
            </div>
            <label>Mobile:</label>
            <input type="text" v-model="input.mobile">
            <h2 style="margin-top: 20px">Payee Information</h2>
            <label>Payee:</label>
            <input type="text" v-model="input.payee">
            <br>
            <label>Account:</label>
            <input type="text" v-model="input.payeeAccount">
            <br>
            <label>Address:</label>
            <input type="text" v-model="input.payeeAddress">
            <br>
            <label>City:</label>
            <input type="text" v-model="input.payeeCity">
            <div>
                <div style="float: left; width: 50%">
                    <label>State:</label>
                    <input type="text" v-model="input.payeeState">
                </div>
                <div style="float: right; width: 50%">
                    <label>Postal:</label>
                    <input type="text" v-model="input.payeePostal">
                </div>
            </div>
            <br>
            <button class="submit" type="button" v-on:click="createAccount()">Save</button>
            <p class="warning">{{ output }}</p>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'CreateAccount',
        data() {
            return {
                title: "Create Account",
                input: {
                    first: "",
                    last: "",
                    address: "",
                    city: "",
                    state: "",
                    postal: "",
                    mobile: "",
                    payee: "",
                    payeeAccount: "",
                    payeeAddress: "",
                    payeeCity: "",
                    payeeState: "",
                    payeePostal: ""
                },
                output: ""
            }
        },
        methods: {
            createAccount() {
                var allgood = true
                for (var field in this.input) {
                    if (!this.input.hasOwnProperty(field)) continue
                    if (this.input[field] == "") {
                        allgood = false
                        break
                    }
                }

                if (allgood) {
                    this.output = ""
                    //TODO ajax?
                } else {
                    this.output = "Please fill in all fields."
                }
            }
        }
    }
</script>

<style>
    h2 {
        text-align: center;
    }
</style>
