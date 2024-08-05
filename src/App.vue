<script setup lang="ts">
import { onMounted, ref } from 'vue';

// 반응형 속성
const count = ref(0);
const increment = () => count.value++;

// LifeCycle
onMounted(() => {
  console.log(`초기 값은 ${count.value} 입니다.`);
});
</script>
<template>
  <button @click="increment">강화하기 {{ count }}</button>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
