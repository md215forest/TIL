<script setup>
import { ref, computed } from 'vue'
const count = ref(0)
const evaluation = computed(() => {
  console.log('computed evaluation')
  return count.value > 3 ? 'Good' : 'Bad'
})
evaluation.value = 'Very Good'
console.log('evaluation', evaluation.value)
</script>
<template>
  <p>{{ count > 3 ? 'Good' : 'Bad' }}</p>
  <p>{{ evaluation }}</p>
  <p>{{ count }}</p>
  <button @click="count++">+1</button>
</template>
