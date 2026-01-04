<script setup lang="ts">
import { ref, nextTick } from 'vue';

const count = ref(2);
let prevValue = ref(0);

async function increment() {
  count.value++;
  prevValue.value = count.value * 2;
  count.value ++;
}

</script>

<template>
  <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4">
    <h1 class="font-bold mb-4">Reactivity Fundamentals:</h1>
    <p class="mb-4">Count: {{ count }}</p>
    <button @click="increment" class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">
      Increment {{ count }}
    </button>

    <h1 class="font-bold mt-8 mb-4">Next Tick Example:</h1>
    <p>Previous Value * 2 = {{ prevValue }}</p>


  </div>
</template>

<style scoped></style>
