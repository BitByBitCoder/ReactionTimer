<script setup>
import TheWelcome from '../components/TheWelcome.vue'
let isPlaying = false
let delay = null

function start() {
  isPlaying = true
  delay = 2000 + Math.floor(Math.random() * 5000)
  console.log(delay)
}
</script>

<template>
  <main id="center">
    <div>
      <button @click="start">Play</button>
    </div>
  </main>
</template>

<style scoped>
#center {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
