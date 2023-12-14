<template lang="">
  <div>
  </div>
</template>
<script>
import { reactive, ref } from 'vue';

export default {
  setup() {
    //ref -> Object에서 사용
    const count = ref(0);
    const state = reactive({
      count,
    });
    count.value++;
    console.log(count.value);
    console.log(state.count);

    //ref -> Array에서 사용
    const message = ref('Hello');
    const arr = reactive([message]);
    console.log('arr[0]: ', arr[0].value);

    return {
    };
  }
}
</script>
<style lang="">
  
</style>