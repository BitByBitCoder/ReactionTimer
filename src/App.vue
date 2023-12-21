<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Block from './components/Block.vue'
import { ref } from 'vue'
let isPlaying = ref(false)
let time = ref(0)
let myVar = ref(0)
let notDisable = ref('notDisable')

let disable = false
function start() {
  disable = true
  let random = 2000 + Math.floor(Math.random() * 3000)
  console.log(random)
  var stop = setTimeout(execute, random)
}

function execute() {
  console.log('execute')
  isPlaying.value = !isPlaying.value
  myVar.value = setInterval(myTimer, 10)
}
function myTimer() {
  time.value = time.value + 1
}

function clearInterval() {
  notDisable.value = 'display'
  console.log('display')
  clearTimeout(myVar.value)
}

function click() {
  console.log('some event')
}
function restert() {
  time.value = 0
  disable = false
  notDisable.value = 'notDisable'
  isPlaying.value = false
}
</script>

<template>
  <div class="center">
    <div>
      <div class="center"><button :disabled="disable" @click="start">Play</button></div>
      <div :class="notDisable"><button @click="restert">Restart</button></div>
      <div class="center"><Block @some-event="clearInterval" v-if="isPlaying" /></div>

      <h1>{{ time }}</h1>
    </div>
  </div>
</template>

<style scoped>
.center {
  display: flex;
  justify-content: center;
  align-content: center;
}
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}

.notDisable {
  display: none;
}
.display {
  display: block;
}

.theisthegitchang {
  background: gray;
}
</style>
