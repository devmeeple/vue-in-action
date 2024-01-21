<template>
  <div>
    <!--    <div v-if="isVisible" class="red"></div>-->
    <!--    <div v-if="isVisible === true" class="blue"></div>-->
    <!--    <div v-else class="yellow"></div>-->

    <!-- 변수 값이 아닌 v-if 문 안에 담긴 조건이 참 일때 실행 -->
    <!--    <div v-if="count > 1" class="red"></div>-->
    <!--    <div v-else class="blue"></div>-->

    <!--    <button @click="count++">증가</button>-->
    <!--    <button @click="count&#45;&#45;">감소</button>-->

    <div v-show="isVisible" class="red"></div>
    <div v-show="!isVisible" class="blue"></div>

    <div v-if="isVisible" class="yellow"></div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      isVisible: false,
      count: 0,
    };
  },
});
</script>

<style scoped>
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

.yellow {
  background-color: yellow;
  width: 100px;
  height: 100px;
}
</style>
