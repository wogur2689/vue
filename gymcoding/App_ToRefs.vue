<template lang="">
  <div>
    <p>author: {{author}}</p>
    <p>title: {{title}}</p>
  </div>
</template>
<script>
import { reactive, ref, toRef, toRefs } from 'vue';

export default {
  setup() {
    const book = reactive({
      author: 'Vue Team',
      year: '2020',
      title: 'Vue 3 Guide',
      description: '당신은 지금 바로 이 책을 읽습니다 :)',
      price: '무료'
    });

    //구조분해 할당(ES6문법)
    //속성을 재할당 했기 때문에 반응성을 잃어버림.
    //그래서 toRefs()사용하면 동기화가 되어 반응형이 적용됨.
    //const {author, title} = toRefs(book);

    //하나씩 같고 오고 싶으면 toRef 사용
    const author = toRef(book, 'author');
    const title = toRef(book, 'title');

    return {
      author, title
    };
  }
}
</script>
<style lang="">
  
</style>