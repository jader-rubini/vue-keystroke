<script setup>
import { ref } from 'vue'
import KeyDisplay from './components/KeyDisplay.vue'

const keyName = ref(null)
const keyCode = ref(null)

function onKeyDown(e) {
  keyName.value = e.key === ' ' ? 'Space' : e.key
  keyCode.value = e.keyCode
}

window.addEventListener('keydown', onKeyDown)
</script>

<template>
  <header>
    <h1>Press any key</h1>
  </header>

  <section>
    <key-display label="Key name">
      <slot v-if="keyName">{{ keyName }}</slot>
    </key-display>

    <key-display label="Key code">
      <slot v-if="keyCode">{{ keyCode }}</slot>
    </key-display>
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
