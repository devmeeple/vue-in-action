<script setup lang="ts">
import { onBeforeMount, onMounted, ref } from 'vue';

// 반응형 속성
const count = ref(0);
console.log(count.value);
console.log('LifeCycle is Setup');

const test = () => console.log('함수 호출');

// LifeCycle
onBeforeMount(() => {
  test();
  console.log('LifeCycle onBeforeMount', document.querySelector('h1'));
});

onMounted(() => {
  test();
  console.log(`LifeCycle onMounted`, document.querySelector('h1'));
});
</script>
<template>
  <h1>LifeCycle 테스트</h1>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
