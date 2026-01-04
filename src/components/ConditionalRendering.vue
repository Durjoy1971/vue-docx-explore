<script setup lang="ts">
import { ref } from 'vue';

let awesome = ref(true);
let good = ref(true);
</script>

<template>
  <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4">
    <button v-on:click="awesome = !awesome" class="cursor-pointer">Toogle Awesome</button>
    <button v-on:click="good = !good" class="cursor-pointer mt-2">Toogle Good</button>
    <h1 v-if="awesome && good">Vue is awesome and good</h1>
    <h1 v-else-if="awesome">Vue is awesome but not good</h1>
    <h1 v-else-if="good">Vue is not awesome but good</h1>
    <h1 v-else>Vue is neither awesome nor good</h1>
  </div>
</template>

<style scoped></style>
