<script setup lang="ts">
import { reactive, ref } from 'vue'

const message = ref('')
const another_msg = ref('')
const state = reactive({
    multiline: '',
    checked: false,
})
</script>

<template>
    <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4 gap-4">
        <p>Message is: {{ message }}</p>
        <input v-model="message" placeholder="edit me" class="border max-w-lg" />
        <p>Another Message is: {{ another_msg }}</p>
        <input :value="another_msg" @input="(event) => (another_msg = (event.target as HTMLInputElement).value)"
            placeholder="edit me too" class="border max-w-lg" />

        <span>Multiline message is: {{ state.multiline }}</span>
        <textarea v-model="state.multiline" placeholder="add multiple lines"
            class="border max-w-md px-2 py-1"></textarea>

        <div class="flex gap-4">
            <input type="checkbox" id="checkbox" v-model="state.checked" />
            <label for="checkbox">{{ state.checked }}</label>
        </div>
    </div>
</template>

<style scoped></style>
