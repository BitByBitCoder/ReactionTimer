<script setup>
import { ref } from 'vue'
import { onMounted } from 'vue'

defineProps({
  result: Number
})
let rank = ref('')

onMounted(() => {
  // Convert result to a number before comparison
  // const resultValue = parseInt(result, 10)
  // if (resultValue < 250) {
  //   rank.value = 'Ninja Fingers'
  // } else if (resultValue < 400) {
  //   rank.value = 'Rapid Reflex'
  // } else {
  //   rank.value = 'Snail Pace'
  // }
})
</script>
<template>
  <div>
    <h1>hello</h1>
    <h1>Your score {{ result }} ms</h1>
    <p class="rank">Rank {{ rank }}</p>
  </div>
</template>

<style scoped>
.rank {
  color: aquamarine;
  font-size: 1.4em;
  font-weight: bold;
}
</style>
