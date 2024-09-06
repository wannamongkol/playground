<script setup lang="ts">
import { useCounterStore } from "./stores/Counter.js"
import { RouterView } from 'vue-router'

const counter = useCounterStore()
</script>

<template>
     <RouterView>
     </RouterView>
</template>

<style scoped>
</style>
