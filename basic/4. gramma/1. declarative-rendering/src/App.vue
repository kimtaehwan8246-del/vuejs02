<template>
  <div id="date">
    {{ date }}
  </div>
  <div id="date2">
    {{ date2 }}
  </div>
</template>

<script>
export default {
  // Composition API
  //변수를 만들고 상수형으로 데이터 입력(반응형 X), return 해야 사용가능
  setup() {
    const date = Date().toString();
    return {
      date,
    };
  },

  // Option API
  //자동으로 반영됨
  data() {
    return {
      date2: Date().toString(),
    };
  },
};
</script>
