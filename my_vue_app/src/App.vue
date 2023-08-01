<script setup>

import TestComponent from "@components/TestComponent/TestComponent.vue";
import ComponentLifeCycle from "@components/TestComponent/ComponentLifeCycle.vue";
</script>

<template>
 <div>
  <h1>
    Hello, This is my Vue APP!
  </h1>
 </div>
  <div>
    <span v-text="msg"> </span>
    &nbsp;
    <span> {{ msg2 }} </span>
  </div>
  <TestComponent/>
  <ComponentLifeCycle/>
 <br/>
<!--<TestComponent/>
 <ComponentLifeCycle/>-->
</template>
<script>
import { ref } from "vue";
export default {
    data () {
      const msg = ref( "Hello World")
      const msg2 = ref("I'm Younghwan")
      return { msg, msg2 }
    }
  }
</script>


<style scoped>


</style>
