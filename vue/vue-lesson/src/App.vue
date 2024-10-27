<script setup>
import { ref, watch, watchEffect } from 'vue'
const count = ref(0)
const count1 = ref(0)
const count2 = ref(0)

watch(
  () => {
    console.log('watch first aruguement')
    return count.value
  },
  (newValue, oldValue) => {
    console.log('watch')
    console.log(newValue, oldValue)
  },
  {
    immediate: false,
  },
)

watchEffect(() => {
  console.log('watchEffect')
  console.log(count.value)
  setTimeout(() => {
    console.log('after 1s')
    console.log(count.value)
  }, 1000)
})
</script>
<template>
  <p>{{ count }}</p>
  <p>{{ count1 }}</p>
  <p>{{ count2 }}</p>
  <button @click="count++">Increment</button>
  <button @click="count1++">Increment 1</button>
  <button @click="count2++">Increment 2</button>
</template>
