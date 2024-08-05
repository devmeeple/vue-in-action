<template>
  <div>{{ sendProps1 }}</div>
  <div>{{ sendProps2 }}</div>
  <ul>
    <li>{{ sendProps3.id }}</li>
    <li>{{ sendProps3.title }}</li>
    <li>{{ sendProps3.description }}</li>
  </ul>
</template>

<script setup lang="ts">
import type { Post } from '@/App.vue';
import { toRefs } from 'vue';

// 1. Composition API
// 1-1. Props 받은 데이터 타입을 지정한다.

interface Props {
  sendProps1: String;
  sendProps2: Number;
  sendProps3: Post;
}

// defineProps 내장함수 사용
// toRefs: 전달 받은 데이터를 템플릿에서 호출해서 사용한다.
const props = defineProps<Props>();
const { sendProps1, sendProps2, sendProps3 } = toRefs(props);
</script>

<style scoped></style>
