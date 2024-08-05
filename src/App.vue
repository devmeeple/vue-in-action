<template>
  <div>
    <h2>v-model 양방향 바인딩</h2>
    <input type="text" v-model="inputValue1" />
    <!--    <input type="text" :value="inputValue2" @input="inputValue2 = $event.target.value" />-->
  </div>
  <div>{{ inputValue1 }}</div>
  <div>{{ inputValue2 }}</div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const inputValue1 = ref('');
const inputValue2 = ref('');
</script>

<style scoped></style>
