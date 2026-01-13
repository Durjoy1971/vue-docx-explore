<script setup lang="ts">
import { reactive, ref } from 'vue';

const count = ref(0)

function reduceByTwo(event: Event) {
  count.value = count.value - 2;
}

function say(message: string) {
  alert(message);
}

</script>

<template>
  <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4">
    <button
      class="bg-blue-500 text-white px-4 py-2 rounded mb-4"
      @click="count++"
    >
      Increment Count
    </button>
    <button
      class="bg-red-500 text-white px-4 py-2 rounded mb-4"
      @click="reduceByTwo"
    >
      Decrement Count by 2
    </button>
    <p> Count is : {{ count }}</p>
    <button @click="say('hello')" class="bg-green-500 text-white px-4 py-2 rounded my-2">Say hello</button>
    <button @click="say('bye')" class="bg-red-500 text-white px-4 py-2 rounded my-2">Say bye</button>
  </div>
</template>

<style scoped></style>
