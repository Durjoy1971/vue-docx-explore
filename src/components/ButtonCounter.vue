<script setup lang="ts">
import { ref } from 'vue'
const counter = ref(0)
</script>

<template>
  <div>
    <button @click="counter++" class="p-4 border bg-white">
      You clicked me {{ counter }} times.
    </button>
  </div>
</template>

<style scoped></style>