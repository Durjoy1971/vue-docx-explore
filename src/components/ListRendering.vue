<script setup lang="ts">
import { reactive, ref } from 'vue';
const items = ref<string[]>(['Item 1', 'Item 2', 'Item 3']);
const nestedItems = ref<string[][]>([
  ['Nested Item 1.1', 'Nested Item 1.2'],
  ['Nested Item 2.1', 'Nested Item 2.2'],
]);
const myObject = reactive({
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
})

</script>

<template>
  <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4">
    <ul>
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>
    <div class="mt-4">
      <div v-for="(sublist, subIndex) in nestedItems" :key="subIndex" class="mb-2">
        <strong>Sublist {{ subIndex + 1 }}:</strong>
        <ul>
          <li v-for="(subItem, itemIndex) in sublist" :key="itemIndex">{{ subItem }}</li>
        </ul>
      </div>
    </div>
    <div class="mt-4">
      <ul>
        <li v-for="(value, key) in myObject" :key="key">
          {{ key }} : {{ value }}
        </li>
      </ul>
    </div>

  </div>



</template>

<style scoped></style>
