<template>
  <div>{{ rawHtml }}</div>
  <div>{{ rawHtml2 }}</div>
  <h1 v-html="rawHtml2"></h1>

  <h2 v-bind:class="{ active: isActive }">클래스 바인딩</h2>
  <h2 :class="{ active: isActive }">클래스 바인딩 축약</h2>
  <button @click="change">버튼</button>

  <h3 style="color: red">스타일 바인딩: 인라인</h3>
  <h3 :style="{ color: fontColor }">스타일 바인딩</h3>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      rawHtml: '선언적 렌더링',
      rawHtml2: '<span style="color: red">빨간색</span>',
      isActive: false,
      fontColor: 'green',
    };
  },
  methods: {
    change() {
      this.isActive = !this.isActive;
    },
  },
});
</script>

<style scoped>
h2.active {
  color: green;
}
</style>
