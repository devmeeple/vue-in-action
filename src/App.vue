<template>
  <div>
    <h1>+{{ count }}강</h1>
    <button @click="count++">인라인 핸들러</button>
  </div>

  <div>
    <h1>{{ name }}</h1>
    <button @click="changeName">메서드 핸들러</button>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const count = ref(0);
const name = ref('성공');

const changeName = () => {
  name.value = '실패';
};
</script>

<style scoped></style>
