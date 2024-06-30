<script setup lang="ts">
// Nuxtはオートインポートなので以下は必要ない
// import { ref, computed } from "vue";

// 乱数を取得
const widthInit = Math.round(Math.random() * 10);
const heightInit = Math.round(Math.random() * 10);

// リアクティブ変数 ref
const width = ref(widthInit);
const height = ref(heightInit);

// refによって用意したリアクティブな変数の値を変更するときは.valueプロパティにアクセスする
// computedは算出プロパティ。リアクティブな変数をもとに変数を設定する
const area = computed((): number => {
  return width.value * height.value;
});

if (typeof window !== "undefined") {
  setInterval((): void => {
    width.value = Math.round(Math.random() * 10);
    height.value = Math.round(Math.random() * 10);
  }, 10000);
}
</script>
<template>
  <p>縦{{ height }}で横が{{ width }}の長方形の面積は{{ area }}</p>
</template>
