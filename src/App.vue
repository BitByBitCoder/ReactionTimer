<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Block from './components/Block.vue'
import { ref } from 'vue'

let isPlaying = ref(false)
let delay = null
function start() {
  delay = 2000 + Math.random() * 5000
  isPlaying.value = true
  console.log(isPlaying.value, delay)
}

function test() {
  isPlaying.value = false
}
</script>

<template>
  <div class="br">
    <div class="center">
      <div>
        <div class="center">
          <button :disabled="isPlaying" @click="start">Start</button>
        </div>
        <Block v-if="isPlaying" :delay="delay" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.br {
  margin-top: 100px;
}
.center {
  display: flex;
  justify-content: center;
  align-content: center;
}
header {
  line-height: 1.5;
  max-height: 100vh;
}
\ .logo {
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
