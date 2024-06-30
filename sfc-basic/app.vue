<script setup lang="ts">
// Nuxtはオートインポートなので以下は必要ない
// import { ref, computed } from "vue";

// 乱数を取得
const widthInit = Math.round(Math.random() * 10);
const heightInit = Math.round(Math.random() * 10);

// オブジェクトをまとめてリアクティブにできるreactive()
const rectangle = reactive({
  width: widthInit,
  height: heightInit,
});
// Vueではref()とreactive()の二種類のメソッドが利用できる。
// 使い分けとしては、まずref()をおすすめ。理由はその方がコードの見通しが良くなる

// computedは算出プロパティ。リアクティブな変数をもとに変数を設定する
const area = computed((): number => {
  return rectangle.width * rectangle.height;
});

if (typeof window !== "undefined") {
  setInterval((): void => {
    rectangle.width = Math.round(Math.random() * 10);
    rectangle.height = Math.round(Math.random() * 10);
  }, 10000);
}
</script>
<template>
  <p>
    縦{{ rectangle..height }}で横が{{ rectangle.width }}の長方形の面積は{{
      area
    }}
  </p>
</template>
