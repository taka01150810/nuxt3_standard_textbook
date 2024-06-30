<script setup lang="ts">
const msg = ref("まだ");
const onButtonClick = (label: string, point: number): void => {
  msg.value = `${label}と${point}`;
};
</script>

<template>
  <p>{{ msg }}</p>
  <button v-on:click="onButtonClick('ハロー', 45)">こんにちは</button>
</template>
