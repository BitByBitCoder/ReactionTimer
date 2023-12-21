<template>
  <div @click="$emit('someEvent')" class="square">click me</div>
</template>

<script setup>
import { ref, onMounted, onUpdated } from 'vue'

const el = ref()

onMounted(() => {
  console.log('mounted')
})
onUpdated(() => {
  console.log('updated')
})

const props = defineProps({
  isPlaying: Boolean
})
function clickme() {
  console.log('yuou click')
}
</script>

<style scoped>
.square {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 10px;
  padding: 10px;
  height: 300px;
  width: 300px;
  background-color: aquamarine;
  border-radius: 10%;
}
</style>
