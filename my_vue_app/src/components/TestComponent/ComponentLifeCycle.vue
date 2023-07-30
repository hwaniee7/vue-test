<template>
    <h1> LifeCycle Test </h1>
</template>
<script>
    export default {
        beforeCreate() {
            console.log(1)
        },
        created() {
            console.log(2)
        },
        beforeMount() {
            console.log(3)

        },
        mounted() {
            console.log(4)
        },
    }
</script>
<style>
</style>