<script setup lang="ts">
import { ref, computed } from 'vue'

const count = ref(0)
let word = ref("")
const calc = computed(() =>{
  let res = 0
  let lowerWord = word.value.toLowerCase();
  for (let i = 0;i < lowerWord.length; i++) {
    if (lowerWord[i].toLowerCase() == lowerWord[i].toUpperCase()) continue;
    res += lowerWord.charCodeAt(i) - "a".charCodeAt(0) + 1
  }
  return res
})
</script>

<template>
  <p>
    <input v-model="word" />
  </p>
  <p>{{calc}}</p>
  <p>{{word}}</p>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
