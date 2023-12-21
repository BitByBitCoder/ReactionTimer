<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const props = defineProps(['delay'])
function listeningclick() {
  console.log('event')
}
onMounted(() => {
  console.log('mounted')
  setTimeout(() => {
    showBlock.value = true
    startTimer()
  }, 3000)
})

onUnmounted(() => {
  console.log('unmounted')
})
let showBlock = ref(false)
let timer = ref(null)
let reactionTime = ref(0)
function startTimer() {
  timer.value = setInterval(() => {
    reactionTime.value += 10
  }, 10)
}

function stopTimer() {
  clearInterval(timer.value)
  console.log(reactionTime.value)
}
</script>
<template>
  <div>
    <div @click="stopTimer" class="block" v-if="showBlock">click Me</div>
    <div>{{ props.helloprops }}</div>
  </div>
</template>

<style scoped>
.block {
  width: 400px;
  border-radius: 20px;
  background: rgb(92, 92, 173);
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
