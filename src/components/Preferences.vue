<template>
    <div id="preferences">
        <h2 id="subtitle">{{ title }}</h2>
        <form class="small-form">
            <label>Round to the nearest:</label>
            <div id="roundingoptions">
                <div>
                    <input type="radio" name="rounding" value="25" v-model="input.rounding">
                    <label>Quarter</label>
                </div>
                <div>
                    <input type="radio" name="rounding" value="50" v-model="input.rounding">
                    <label>Fifty Cents</label>
                </div>
                <div>
                    <input type="radio" name="rounding" value="100" v-model="input.rounding">
                    <label>Dollar</label>
                </div>
            </div>
            <br>
            <label>Maximum rounded per month:</label>
            <input type="number" v-model="input.maximum">$
            <button type="button" v-on:click="save()">Save</button>
            <p class="warning">{{ output }}</p>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'preferences',
        data() {
            return {
                title: "Preferences",
                input: {
                    rounding: "",
                    maximum: ""
                },
                output: ""
            }
        },
        methods: {
            save() {
                // Save options
                this.output = "Options saved."
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
