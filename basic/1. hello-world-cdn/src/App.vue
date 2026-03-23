<template>
  <div>Hello Vue 3 NPM</div>
</template>

<style>
#app {
  font-size: 3em;
}
</style>

<script>
export default {
  data() {
    return {
      username: '',
    };
  },
  methods: {
    fetchUser() {
      //사용자 이름 설정 this.fechUser() 호출 위치
      this.username = '김태환';
      console.log('데이터 로딩 완료');
    },
  },
  //created() : 데이터 초기화 시점
  created() {
    console.log('컴포넌트 생성됨');
    this.fetchUser();
  },
  //mounted() : DOM 접근가능시점
  mounted() {
    console.log('DOM 렌더링 완료');
  },
};
</script>
