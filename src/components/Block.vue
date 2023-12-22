<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
const emit = defineEmits(['end'])
const props = defineProps(['delay'])

onMounted(() => {
  console.log(props.delay)
  setTimeout(() => {
    showBlock.value = true
    startTimer()
  }, props.delay)
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
  emit('end', reactionTime.value)
}
</script>
<template>
  <div>
    <div @click="stopTimer" class="block" v-if="showBlock">click Me</div>
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
