<script setup lang="ts">
const message = 'Hello World'
const rawHtml = '<span style="color: red">This should be red.</span>'
const url = 'https://vuejs.org'
const isButtonDisabled = true
const isAnotherButtonDisabled = false
const date = '2024-06-15T13:45:30Z'
const seen = true

function formatDate(dateString: string): string {
    const options: Intl.DateTimeFormatOptions = {
        year: 'numeric',
        month: 'long',
        day: 'numeric',
    }
    const date = new Date(dateString)
    return date.toLocaleDateString(undefined, options)
}

function toTitleDate(dateString: string): string {
    const date = new Date(dateString)
    return date.toDateString()
}

function doSomething() {
    alert('You clicked me!')
}

function onSubmit() {
    alert('Form submitted!')
}
</script>

<template>
    <div class="bg-yellow-200 flex flex-col justify-center h-screen p-4 font">
        <h1 class="font-bold">Text Interpolation:</h1>
        <p>Message: {{ message }}</p>
        <h1 class="font-bold">Raw HTML:</h1>
        <p>Using text interpolation: {{ rawHtml }}</p>
        <p>Using v-html directive: <span v-html="rawHtml"></span></p>
        <h1 class="font-bold">Attribute Bindings (With Arguments):</h1>
        <p>Using v-bind directive: <a v-bind:href="url" target="_blank">Click me</a></p>
        <p>Using shorthand syntax: <a :href="url" target="_blank">Click me</a></p>
        <h1 class="font-bold">Boolean Attributes:</h1>
        <button v-bind:disabled="isButtonDisabled" :class="{
            'cursor-not-allowed opacity-50': isButtonDisabled,
            'cursor-pointer opacity-100': !isButtonDisabled,
        }">
            Disable Button
        </button>
        <button :disabled="isAnotherButtonDisabled" :class="[
            'px-4 py-2 rounded',
            isAnotherButtonDisabled
                ? 'cursor-not-allowed opacity-50'
                : 'cursor-pointer opacity-100'
        ]">
            Workable Button
        </button>
        <h1 class="font-bold">Calling Functions:</h1>
        <time :title="toTitleDate(date)" :datetime="date">
            {{ formatDate(date) }}
        </time>
        <h1 class="font-bold">Directives:</h1>
        <p v-if="seen">Now you see me</p>

        <h1 class="font-bold">Arguments</h1>
        <button @click="doSomething" class="cursor-pointer text-blue-500">Click Me</button>

        <form @submit.prevent="onSubmit">
            <label for="name" class="block font-medium mb-2">Name:</label>
            <input type="text" id="name" name="name" class="border border-gray-300 rounded px-3 py-2 w-full"
                placeholder="Enter your name" />
            <button type="submit"
                class="mt-4 bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">Submit</button>
        </form>

    </div>
</template>