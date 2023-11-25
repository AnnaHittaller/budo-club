<script setup>
import { RouterLink } from 'vue-router';
import { defineProps, computed } from 'vue';


const props = defineProps({
    title: {
        type: String,
        required: true
    },
    text: {
        type: String,
        required: true
    },
    img: {
        type: String,
        required: true
    },
    buttonLink: {
        type: String,
        required: true
    }
})


const imageSrc = computed(() => `/assets/${props.img}`);

</script>

<template>
    <div class="flex flex-col items-center bg-white text-gray-950 max-w-xs">
        <img :src="imageSrc" alt="Budo Club Shogun Euskirchen"
            class="bg-gray-500 aspect-[2/1] w-full object-cover grayscale">
        <div class="bg-red-500 h-1 w-full mb-4"></div>
        <div class="flex flex-col flex-grow justify-between items-center">
            <div class="px-4">
                <h3>{{ props.title }}</h3>
                <p>{{ props.text }}</p>
            </div>
            <RouterLink :to="{ path: '/training', hash: props.buttonLink }">
                <button class="btn my-4 justify-self-end">Mehr erfahren</button>
            </RouterLink>
        </div>
    </div>
</template>

<style scoped></style>