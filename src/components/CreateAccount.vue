<template>
    <div id="login">
        <h2 id="subtitle">{{ title }}</h2>
        <form class="small-form">
            <label>Username:</label>
            <input type="text">
            <br>
            <label>Password:</label>
            <input type="password">
            <br>
            <br>
            <br>
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

                if (true) {
                    this.output = ""
                    //TODO ajax?
                    this.$emit("changepage","overview")
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
