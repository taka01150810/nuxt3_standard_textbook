<script setup lang="ts">
const msg = ref("まだ");
const onButtonClick = (event: Event): void => {
  msg.value = event + "イベントクリック";
};
</script>

<template>
  <p>{{ msg }}</p>
  <button v-on:click="onButtonClick">こんにちは</button>
</template>
