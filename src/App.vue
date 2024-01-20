<!-- Options API Style -->
<template>
  <div>{{ count }}</div>
  <h1>Vue.js Life cycle</h1>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      count: 0,
    };
  },
  beforeCreate() {
    console.log('컴포넌트 생성 전: beforeCreate 시작', this.count); // undefined
    // this.test(); [에러] 컴포넌트 생성 전에 함수 접근 불가
  },
  created() {
    console.log('컴포넌트 생성된 직후: created', this.count); // 0
    this.test(); // [성공] 컴포넌트 생성 후 함수 접근 가능
  },
  // beforeMount() {
  //   console.log('UI 생성 전: beforeMount', document.querySelector('h1'));
  // },
  // mounted() {
  //   console.log('UI 생성 후: mounted', document.querySelector('h1'));
  // },
  methods: {
    test() {
      console.log('test 함수 호출');
    },
  },
});
</script>

<style scoped></style>
