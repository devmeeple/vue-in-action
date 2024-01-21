<template>
  <div>
    <li v-for="book in books" :key="book">
      {{ book }}
    </li>
    <!-- 키 값은 필수, 유니크(고유한 값) 해야 한다 -->
    <div v-for="item in items" :key="item.id">
      <h3>{{ item.title }}</h3>
      <p>{{ item.content }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      books: ['모던 자바스크립트', 'Node.js 백엔드 개발자 되기', '개발자가 되고 싶습니다'],
      items: [
        {
          id: 0,
          title: '코어 자바크립트',
          content: '핵심 개념과 동작 원리로 이해하는 자바스크립트 프로그래밍',
        },
        {
          id: 1,
          title: 'NestJS로 배우는 백엔드 프로그래밍',
          content: '가장 진보한 프레임워크로 백엔드에 입문하는 방법',
        },
      ],
    };
  },
});
</script>

<style scoped></style>
