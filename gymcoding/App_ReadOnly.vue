<template lang="">
  <div>
  </div>
</template>
<script>
import { reactive, readonly } from 'vue';

export default {
  setup() {
    const original = reactive({
      count: 0,
    });
    const copy = readonly(original);
    original.count++;
    copy.count++; //readonly는 값 변경 불가능 경고 출력
    console.log(original.count);
    console.log(copy.count);
    return {
     
    };
  }
}
</script>
<style lang="">
  
</style>