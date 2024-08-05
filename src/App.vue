<template>
  <button @click="changeMessage">{{ message }}</button>
  <p>{{ watchMessage }}</p>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue';

const message = ref('[Watch 오리지널 문구] 놀러오세요 동물의 숲');
const watchMessage = ref('');

const changeMessage = () => {
  console.log('함수 호출');
  message.value = '변경된 메세지';
};

watch(message, () => {
  watchMessage.value = 'Watch 동작';
});
</script>

<style scoped></style>
