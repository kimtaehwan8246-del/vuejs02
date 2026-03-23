<template>
  <div style="width: 200px">
    <ol>
      <li v-for="item in items">{{ item }}</li>
      <!-- item 배열 안에 있는 객체들 하나씩 꺼내서 출력 -->
    </ol>
  </div>
</template>

<script>
import { reactive } from 'vue';

export default {
  // Composition API
  setup() {
    //ref() 없으니까 반응형 아님
    const items = reactive({ 1: '1번 객체', 2: '2번 객체', 3: '3번 객체' });
    return {
      items, // = items++
    };
  },
};
</script>
