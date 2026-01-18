<script setup lang="ts">
import { ref } from 'vue'
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'

const posts = ref([
  { id: 1, title: 'My journey with Vue' },
  { id: 2, title: 'Blogging with Vue' },
  { id: 3, title: 'Why Vue is so fun' },
])
</script>

<template>
  <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4 gap-4">
    <h1>Here is a child component</h1>
    <ButtonCounter />
    <BlogPost v-for="post in posts" :key="post.id" :title="post.title" />
  </div>
</template>

<style scoped></style>
