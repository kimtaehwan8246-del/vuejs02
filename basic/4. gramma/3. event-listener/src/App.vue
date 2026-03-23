<!-- 이벤트 리스너(@)를 이용한 사용자의 입력을 처리하는 방법
  HTML 태그가 발생시키는 이벤트를 캡쳐하여 지정된 스크립트를 수행하거나
  함수를 호출하기 위해서 v-on 디렉티브를 사용한다.
  사용자가 버튼을 클릭했을때 click 이벤트를 발생한다.
  발생한 이벤트를 캡쳐하기 위해 두가지 방식으로 캡쳐링 할 수 있다
  1) v-on:click ="스크립트 코드 또는 함수"
  2) @click ="스크립트 코드 또는 함수"
-->

<template>
  <p>{{ counter + counter2 }}</p>
  <!-- counter 변수를 직접 참조하여 숫자를 증가 -->
  <button @click="counter++">클릭하면 숫자가 올라갑니다.</button>
  <!-- onClick 함수 호출하여 숫자 증가 -->
  <button @click="onClick2">클릭하면 숫자가 올라갑니다.</button>
</template>

<script>
import { ref } from 'vue';

export default {
  data() {
    return {
      counter2: 0,
      //자동반응형 => this.로 다시 접근
    };
  },
  setup() {
    let counter = ref(0);
    //counter 변수는 ref를 통해 프록시객체로 변환되어 관리된다.
    //반응형
    const onClick = (evt) => {
      //evt : 이벤트 객체를 받는 파라미터
      if (evt) {
        evt.preventDefault();
        counter.value++;
        //ref 값 변경
      }
    };
    return {
      counter,
      onClick,
    };
  },
  methods: {
    onClick2: function (evt) {
      if (evt) {
        evt.preventDefault();
      }
      this.counter2++;
    },
  },
};
</script>
