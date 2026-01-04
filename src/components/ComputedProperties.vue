<script setup lang="ts">
import { reactive, computed } from 'vue';

const author = reactive({
  name: 'Jane Doe',
  books: [
    { title: 'Vue.js Basics', year: 2020 },
    { title: 'Advanced Vue.js', year: 2022 },
    { title: 'Mastering Vue.js', year: 2024 },
  ],
})

const publishedBooksMessage = computed(() => {
  return author.books.length > 0
    ? `Author ${author.name} has published ${author.books.length} books.`
    : `Author ${author.name} has not published any books yet.`;
});

</script>

<template>
  <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4">
    <h1 class="font-bold mb-4">Reactivity with Reactive and Computed:</h1>
    <p class="mb-2">Author Name: {{ author.name }}</p>
    <h2 class="font-semibold mb-2">Books Published:</h2>
    <ul class="list-disc list-inside mb-4">
      <li v-for="(book, index) in author.books" :key="index">
        {{ book.title }} ({{ book.year }})
      </li>
    </ul>
    <p class="font-medium">{{ publishedBooksMessage }}</p>

  </div>
</template>

<style scoped></style>
