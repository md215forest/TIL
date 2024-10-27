<script setup>
import { ref } from 'vue'
const vueUrl = ref('http://vuejs.org')
const count = ref(0)
function countUp() {
  // 2づつ加算する
  count.value += 2
}
</script>
<template>
  <p>{{ count }}</p>
  <button @click="count++">button</button>
  <button @click="countUp">button</button>
</template>
