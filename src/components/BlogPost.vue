<script setup lang="ts">
const props = defineProps(['title'])
console.log(props.title);
</script>

<template>
    <h4>{{ title }}</h4>
</template>
