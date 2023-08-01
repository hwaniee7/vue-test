
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
          <br/>
            <div id="data">
                data : {{ data }}
            </div>
          <br/>
            <div class="plusMinusEvent" style="border: solid 1px cornflowerblue">
                <p> count : {{ counter }} </p>
                <div class="btnWrapper">
                    <button class="btn" @click="plus"> + </button>
                    <button class="btn" @click="minus"> - </button>
                </div>
            </div>
          <br/>
            <div class="plusMinusEvent" style="border: solid 1px cornflowerblue">
                <p> count : {{ data2 }} </p>
                <div class="btnWrapper">
                  <button class="btn" @click="data2++"> + </button>
                  <button class="btn" @click="data2--"> + </button>
                </div>
            </div>
            <br/>
          <div v-bind="human">
            <h2> 주소록 1 (v-bind object)</h2>
            <table>
              <thead>
                <tr>
                  <td>번호</td>
                  <td>이름</td>
                  <td>나이</td>
                  <td>주소</td>
                  <td>연락처</td>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>{{ human.id }}</td>
                  <td>{{ human.name }}</td>
                  <td>{{ human.age }}</td>
                  <td>{{ human.addr }}</td>
                  <td>{{ human.phone }}</td>
                </tr>
              </tbody>
            </table>
          </div>
          <div>
            <h2> 주소록 2 (배열, v-for) </h2>
            <table>
              <thead>
              <tr>
                <td>번호</td>
                <td>이름</td>
                <td>나이</td>
                <td>주소</td>
                <td>연락처</td>
              </tr>
              </thead>
              <tbody>
                 <tr v-for="human in humanArray" :key="human.id">
                    <td>{{ human.id }}</td>
                    <td>{{ human.name }}</td>
                    <td>{{ human.age }}</td>
                    <td>{{ human.addr }}</td>
                    <td>{{ human.phone }}</td>
                  </tr>
              </tbody>
            </table>
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
          const human = {
            id: 1,
            name: '홍길동',
            age: 25,
            addr: '서울시',
            phone: '01012345678',

          }
          const humanArray = [
            {
              id: 1,
              name: '홍길동',
              age: 25,
              addr: '서울시',
              phone: '01012345678',

            },
            {
              id: 2,
              name: '이순신',
              age: 30,
              addr: '서울시',
              phone: '01022224444',
            },
            {
              id: 3,
              name: '강감찬',
              age: 31,
              addr: '서울시',
              phone: '01033334444',
            }

          ]
          return {
            date2: Date().toString(),
            human, humanArray
          }
        },


       
    }
</script>
<style>
    .container {
        display: flex;
        flex-direction: column;
      border: solid 1px #f68383;
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