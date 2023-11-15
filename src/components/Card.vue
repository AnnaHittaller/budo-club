<template>
    <div class="flex flex-col items-center bg-white text-gray-950 max-w-sm">
        <img :src="imageSrc" alt="" class="bg-gray-500 aspect-[2/1] w-full object-cover grayscale">
        <div class="bg-red-500 h-1 w-full mb-4"></div>
        <div class="flex flex-col flex-grow justify-between items-center">
            <div class="px-4">
                <h3>{{ props.title }}</h3>
                <p>{{ props.text }}</p>
            </div>
            <RouterLink to="/about">
                <button class="btn my-4 justify-self-end">Mehr erfahren</button>
            </RouterLink>
        </div>
    </div>
</template>
<script setup>
import { RouterLink } from 'vue-router';
import { defineProps, ref } from 'vue';

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
    }

})


const imageSrc = ref(null);

const requireImage = async () => {
    try {
        const imageModule = await import(`../assets/${props.img}`);
        imageSrc.value = imageModule.default;
    } catch (error) {
        console.error(error);
    }
};
requireImage();

</script>

<style scoped></style>