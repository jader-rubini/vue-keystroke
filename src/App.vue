<script setup>
import { ref } from 'vue'
import KeyDisplay from './components/KeyDisplay.vue'

const body = document.querySelector('body')
const keyName = ref(null)
const keyCode = ref(null)
const placeholder = '…'

function onKeyDown(e) {
  keyName.value = e.key === ' ' ? 'Space' : e.key
  keyCode.value = e.keyCode
}

body.addEventListener('keydown', onKeyDown)
</script>

<template>
  <header>
    <h1>Press any key to see the magic happen</h1>
  </header>
  <section>
    <key-display label="Key name">{{ keyName ? keyName : placeholder }}</key-display>
    <key-display label="Key keyCode">{{ keyCode ? keyCode : placeholder }}</key-display>
  </section>
</template>

<style scoped>
h1 {
  line-height: 1.2;
  font-size: 1.5rem;
}

section {
  display: grid;
  gap: 1rem;
  margin-top: 1.5rem;
}

@media (min-width: 480px) {
  section {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
