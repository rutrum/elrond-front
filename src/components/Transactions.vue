<template>
    <div id="Transactions">
        <h2 id="subtitle">{{ title }}</h2>
        <div class="big-form">
            <div id="titlerow">
                <span>Payee</span>
                <span>Account Number</span>
                <span>Amount</span>
            </div>
            <div class="transactionrow" v-for="transaction in transactions" v-bind:key="transaction.id">
                <span v-text="transaction.payee"></span>
                <span v-text="transaction.accountnumber"></span>
                <span v-text="transaction.amount / 100"></span>
            </div>
            <div id="totalsrow">
                <span></span>
                <span></span>
                <span v-text="total"></span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Transactions',
        data() {
            return {
                title: "Transactions",
                transactions: [
                    {
                        id: 1,
                        payee: "Capital One",
                        accountnumber: "258083",
                        amount: 34
                    },
                    {
                        id: 2,
                        payee: "Capital One",
                        accountnumber: "258083",
                        amount: 45
                    },
                    {
                        id: 3,
                        payee: "Capital One",
                        accountnumber: "258083",
                        amount: 87
                    }
                ],
                total: 0
            }
        },
        methods: {
            loadTransactions() {
                // Save options
                this.output = "Information saved."
            },
            calcTotal() {
                for (var i = 0; i < this.transactions.length; i++) {
                    this.total += this.transactions[i].amount;
                }
                this.total /= 100;
            }
        },
        beforeMount(){
            this.calcTotal()
        }
    }
</script>

<style>

    .transactionrow, #titlerow, #totalsrow {
        display: flex;
        align-items: center;
        margin: 10px;
    }
    #titlerow {
        font-weight: bold;
    }
    span {
        display: inline-block;
        width: 33%;
    }

</style>