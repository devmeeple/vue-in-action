<template>
  <div></div>
  <ChildComponent :sendProps1="title" :sendProps2="year" :sendProps3="post" />
</template>

<script setup lang="ts">
import ChildComponent from '@/components/ChildComponent.vue';
import { reactive, ref } from 'vue';

export interface Post {
  id: number;
  title: string;
  description: string;
}

// props 전달할 데이터 정의
const title = ref<string>('부모 컴포넌트에서 선언된 데이터');
const year = ref<number>(2024);

// 객체는 reactive 권장
const post = reactive<Post>({
  id: 1,
  title: '최강야구',
  description: '롯데 상대로 동점홈런을 날리는 이대호',
});
</script>

<style scoped></style>
