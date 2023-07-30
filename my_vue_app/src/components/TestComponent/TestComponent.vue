
<template>
    <div class="container">
        <div>
            <h3>Test Component</h3>
        </div>
        <div class="date_data_container">
            <div id="date"> 
                {{ date }}
            </div>
            <div id="date2">
                {{ date2 }}
            </div>
            <div id="data">
                {{ data }}
            </div>
        </div>
    </div>
   
   

</template>
<script>
    export default {
        // Composition API
        setup() {
            const data = 1
            const date = Date().toString()
            return { data, date }
        },
        // Options API
        data() {    
            return {
                date2: Date().toString()
            }
        }
    }
</script>
<style>
    .container {
        display: flex;
        flex-direction: column;
    }
    .date_data_container {
        display: flex;
        flex-direction: column;
    }
</style>