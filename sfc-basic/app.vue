<script setup lang="ts">
const msg = ref("まだ");
const onButtonClick = (): void => {
  msg.value = "引数なしでクリック";
};
</script>

<template>
  <p>{{ msg }}</p>
  <button v-on:click="onButtonClick">こんにちは</button>
</template>
