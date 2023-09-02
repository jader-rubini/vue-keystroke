<script setup>
import KeyDisplay from './components/KeyDisplay.vue'
</script>

<template>
  <header>
    <h1>Press any key to see the magic happen</h1>
  </header>
  <section>
    <key-display label="Key name"></key-display>
    <key-display label="Key value"></key-display>
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
