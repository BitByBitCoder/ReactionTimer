<script setup>
const props = defineProps(['delay'])
function listeningclick() {
  console.log('event')
}
</script>
<template>
  <div>
    <div @dblclick="listeningclick" class="block">click me</div>
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
