<template>
  <div class="v-render">
    <div class="v-class v-style section">
      <div>{{ rawHtml }}</div>
      <div>{{ rawHtml2 }}</div>
      <h1 v-html="rawHtml2"></h1>
      <h2 :class="{ active: isActive }">클래스 바인딩 테스트</h2>
      <button @click="changeActive">버튼</button>

      <h3 :style="{ color: fontColor, fontSize: fontSize + 'px' }">스타일 바인딩 테스트</h3>
    </div>

    <div class="v-if section">
      <h2>v-if 테스트</h2>

      <div v-if="isVisible" class="red"></div>
      <div v-if="isVisible === true" class="blue"></div>
      <div v-else class="black"></div>

      <h3>v-if 안에 조건식이 참이면 렌더링 된다</h3>
      <div v-if="count >= 1" class="red"></div>
      <div v-else class="blue"></div>
      <button @click="increase">후원하기</button>
      <button @click="decrease">차감하기</button>
    </div>

    <div class="v-show section">
      <h2>v-show 테스트</h2>
      <div v-show="isVisible" class="red"></div>
      <div v-show="!isVisible" class="blue"></div>
      <div v-if="isVisible" class="black"></div>
    </div>

    <div class="v-for section">
      <h1>{{ header }}</h1>
      <ul>
        <li v-for="{ id, label } in items" :key="id">{{ label }}</li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const rawHtml = '이것은 텍스트입니다.';
const rawHtml2 = '<span style="color: red">HTML로 해석하기 위해서는 `v-html`을 사용한다.</span>';
const isActive = ref(false);

const fontColor = '#888888';
const fontSize = 48;

const isVisible = ref(false);
const count = ref(0);
const header = ref('v-for 테스트');
const items = ref([
  { id: 1, label: 'Node.js 백엔드 개발자 되기' },
  { id: 2, label: '객체지향의 사실과 오해' },
]);
const changeActive = () => (isActive.value = !isActive.value);
const increase = () => count.value++;
const decrease = () => count.value--;
</script>

<style scoped>
h2.active {
  color: green;
}

.red {
  background-color: red;
  width: 100px;
  height: 100px;
}

.blue {
  background-color: blue;
  width: 100px;
  height: 100px;
}

.black {
  background-color: black;
  width: 100px;
  height: 100px;
}

.section {
  margin-top: 10px;
}
</style>
