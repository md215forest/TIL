<script setup>
import { ref, computed } from 'vue'
const count = ref(0)
const evaluation = computed(() => {
  console.log('computed evaluation')
  return count.value > 3 ? 'Good' : 'Bad'
})
console.log('evaluation', evaluation.value)
function getEvaluation() {
  console.log(evaluation.value)
}
</script>
<template>
  <p>{{ count > 3 ? 'Good' : 'Bad' }}</p>
  <p>{{ count }}</p>
  <button @click="count++">+1</button>
  <button @click="getEvaluation">get Evaluation</button>
</template>
