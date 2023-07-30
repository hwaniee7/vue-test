
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
            <div class="plusMinusEvent">
                <p> count : {{ counter }} </p>
                <div class="btnWrapper">
                    <button class="btn" @click="plus"> + </button>
                    <button class="btn" @click="minus"> - </button>
                </div>
            </div>
            <div>
                {{ data2 }}
                <button @click="data2++"> + </button>
                <button @click="data2--"> + </button>
            </div>
            
        </div>
    </div>
   
   

</template>
<script>
    import { ref } from 'vue'
    export default {
        // Composition API
        setup() {
            const data = 1
            const data2= ref(0)
            let counter = ref(0)
            const date = Date().toString()
            const plus = (evt) => {
                if(evt) {
                    evt.preventDefault();
                    counter.value++
                }
            }
            const minus = (evt) => {
                if(evt) {
                    evt.preventDefault();
                    counter.value--
                }
            }
            
            return { data, data2, date, counter, plus, minus }
        },
        // Options API
        data() {    
            return {
                date2: Date().toString()
            }
        },
       
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
    .plusMinusEvent{
        display: flex;
        flex-direction: column;
    }
    .btnWrapper {
        display: flex;
    }
    .btn {
        width: 3em;

    }
</style>