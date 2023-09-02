<template>
    <div>
        <p>{{ props.label }}</p>
        <h2>
            <slot>Press any key</slot>
        </h2>
    </div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps(['label'])
</script>

<style scoped>
div {
    padding: 1.5rem;
    border-radius: .65rem / .5rem;
    background-color: var(--color-background-soft);
}

@media (min-width: 900) {
    div {
        padding-inline: 2.5rem
    }
}
</style>