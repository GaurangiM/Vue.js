<template>
    <div>
        <h1>Trade or view your Portfolio</h1>
        <h6>You may save or load your data</h6>
        <h6>Click on 'End Day' to begin a new day !</h6>
        <hr>
        <h6>Your funds: {{ funds | currency }}</h6>
    </div>
    
</template>
<script>
export default {
    computed: {
        funds() {
            return this.$store.getters.funds;
        }
    }
}
</script>