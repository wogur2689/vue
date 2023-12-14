<template lang="">
  <div>
    <p>{{message}}</p>
    <button v-on:click="addMessage">add Click</button>
  </div>
</template>
<script>
import { reactive, ref } from 'vue';

export default {
  setup() {
    let message = ref('Hello Vue!');
    const addMessage = () => {
      message.value = message.value + '!';
    }
    //reactvie함수는 객체타입에만 동작함.
    //기본타입은 ref메소드 사용
    
    return {
      message,
      addMessage
    };
  }
}
</script>
<style lang="">
  
</style>