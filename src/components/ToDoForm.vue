<template>
  <form @submit.prevent="onSubmit">
    <h2 class="label-wrapper">
      <label for="new-todo-input" class="label__lg"> What needs to be done? </label>
    </h2>
    <input
      type="text"
      id="new-todo-input"
      name="new-todo"
      autocomplete="off"
      v-model.lazy.trim="label"
      class="input__lg"
    />
    <button type="submit" class="btn btn__primary btn__lg">Add</button>
  </form>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// 이벤트 정의
const emit = defineEmits(['todo-added']);

// label 변수 정의
const label = ref('');

// onSubmit 함수 정의
const onSubmit = () => {
  if (label.value === '') {
    return '';
  }

  emit('todo-added', label.value);
  label.value = '';
};
</script>
<style scoped></style>
