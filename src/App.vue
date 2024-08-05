<template>
  <h1>{{ text }}</h1>

  <!-- 3번 호출-->
  <h1>changeText 호출 값: {{ changeText() }}</h1>
  <h1>changeText 호출 값: {{ changeText() }}</h1>
  <h1>changeText 호출 값: {{ changeText() }}</h1>

  <!-- Computed 1번만 호출, 캐싱(Cashing) -->
  <h2>{{ computedText }}</h2>
  <h2>{{ computedText }}</h2>
  <h2>{{ computedText }}</h2>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue';

const text = ref('Computed 테스트 데이터');
const changeText = () => {
  console.log(`함수 호출 ${text.value}`);
  return text.value.split('').reverse().join('');
};

const computedText = computed(() => {
  console.log(`Computed 함수 호촐 ${text.value}`);
  return text.value.split('').reverse().join('');
});
</script>

<style scoped></style>
