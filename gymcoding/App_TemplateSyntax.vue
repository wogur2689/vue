<!-- Composition API -->
<template lang="">
  <br>
    <h2>보간법</h2>
    <p>{{message}}</p>
    <p v-once>{{message}}</p>
    <button v-on:Click="message = message + '!'">버튼</button>
    <hr/>
    <h2>v-html</h2>
    <p>{{rawHtml}}</p>
    <p v-html="rawHtml"></p>
    <hr/>
    <h2>속성 바인딩 </h2>
    <div :title="dynamicTitle">마우스를 올려주세요</div>
    <input type="text" value="홍길동" :disabled="isInputDisabled"/>
    <input v-bind="attrs"/>
    <h2>JavaScript</h2>
    {{message.split('').reverse().join('')}}</br>
    {{isInputDisabled ? '예' : '아니요'}}
  </div>
</template>
<script>
import { ref } from 'vue';

export default {
  setup () {
    const message = ref('Hello!');
    const rawHtml = ref('<b>안녕하세요</b>');

    const dynamicTitle = ref('안녕하세요오오!');
    const isInputDisabled = ref(false);
    const attrs = ref({
      type:'text',
      value: '12345678',
      disabled: false
    })

    return {
      message,
      rawHtml,
      dynamicTitle, 
      isInputDisabled
    };
  },
};
</script>
<style>
  
</style>