<!-- Composition API -->
<template lang="">
  <div>
    <h2>반응형 메시지</h2>
    <p>{{reactiveMessage}}</p>
    <button v-on:click="addReactiveMessage">Add Message</button>
    <h2>일반 메시지</h2>
    <p>{{normalMessage}}</p>
    <button v-on:click="addNormalMessage">Add Message</button>
  </div>
</template>
<script>
import { isRef, onMounted, onBeforeMount, ref } from 'vue';

//호출순서
/**
 * 라이플사이클에 따라 setup먼저 호출
 * 그후 beforeMounted -> mounted 순서로 호출
 */
export default {
  setup () {
    console.log('set up');
    //반응형 메세지
    const reactiveMessage = ref('Hello Reactive Message');
    const addReactiveMessage = () => {
      reactiveMessage.value = reactiveMessage.value + '!';
    };
    
    console.log('1 :' + isRef(reactiveMessage));

    //일반 메세지
    let normalMessage = 'Hello Normal Message';
    const addNormalMessage = () => {
      normalMessage = normalMessage + '!';
    }
    
    //반응형api인지 검사
    console.log('2 :' + isRef(normalMessage));

    onMounted(() => {
      console.log('on mounted');
    });

    onBeforeMount(() => {
      console.log('on before mounted');
    });

    
    return {
      reactiveMessage,
      normalMessage,
      addReactiveMessage,
      addNormalMessage
    }
  }
};
</script>
<style>
  
</style>