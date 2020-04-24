<template>
    <div>
        <h1>Trade of View your Portfolio</h1>
        <h6>You may Save & Load your Data</h6>
        <h6>Click on 'End Day' to begin a New Day</h6>
        <hr>
        <p>You Funds: {{ funds | currency }}</p>
    </div>
</template>

<script>
    export default {
        name: "Home",
        computed: {
            funds() {
                return this.$store.getters.funds;
            }
        }
    }
</script>

<style scoped>

</style>