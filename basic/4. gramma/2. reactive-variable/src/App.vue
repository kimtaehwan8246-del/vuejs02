<!-- 데이터 결합을 통한 사용자 입력 처리 예제 
  v-model , v-bind 컴포넌트에서 선언한 변수와 HTML 태그의 속성을 
  결합할수있는 디렉토리
  v-bind 디렉티브는 템플릿을 통해서 변수의 값을 변경시킬수 없다
  v-model은 템플릿을 통해서 변수의 값을 변경시킬수있다
-->

<template>
  <p>줄임말과 원래말을 입력하세요.</p>
  <input type="text" v-bind:value="abbr" />
  <!-- 단방향이라 입력해도 값 안바뀜 -->
  <input type="text" v-model="normal" />
  <hr />
  <abbr v-bind:title="normal">{{ abbr }}</abbr>
  <!-- 마우스 올려놓으면 입력한 값 뜸 -->
</template>

<script>
import { ref } from 'vue';

export default {
  // Composition API
  // const로 변수 선언 후 입력
  // ref()는 반응형
  setup() {
    const abbr = ref('KB');
    const normal = ref('KB Project Team');
    return {
      abbr,
      normal,
    };
  },
};
</script>
