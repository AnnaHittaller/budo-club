<script setup>
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import { ref } from 'vue'
const slider = ref(null)

const slides = [
    { id: '1', title: 'Budo Club Shogun Training', path: 'hero.png' },
    { id: '2', title: 'Budo Club Shogun Training', path: 'Training.png' },
    { id: '3', title: 'Budo Club Shogun Training', path: 'Kindertraining.png' },
    { id: '4', title: 'Budo Club Shogun Training', path: 'Probetraining.png' },
    { id: '5', title: 'Budo Club Shogun Training', path: 'hero.png' },
]

const breakpoints = {
    100: {
        itemsToShow: 1.5,
        snapAlign: 'center',
    },
    // 700px and up
    700: {
        itemsToShow: 3.5,
        snapAlign: 'center',
    },
    // 1024 and up
    1024: {
        itemsToShow: 4.5,
        snapAlign: 'center',
    },
}

const requireImages = async () => {
    try {
        for (const slide of slides) {
            const imageModule = await import(`../assets/${slide.path}`);
            slide.imageSrc = imageModule.default;
            //console.log('Image loaded for slide', slide.id)
        }
    } catch (error) {
        console.error(error);
    }
};

requireImages();

const handleClickSlide = (index) => {
    slider.value.slideTo(index - 1)
}

</script>


<template>
    <Carousel :breakpoints="breakpoints" :wrap-around="false" class="px-10" ref="slider">
        <Slide v-for="slide in slides" :key="slide.id" @click="handleClickSlide(slide.id)">
            <img :src="slide.imageSrc" :alt="slide.title" class="carousel__item" />
        </Slide>

        <template #addons>
            <Navigation />
            <Pagination />
        </template>
    </Carousel>
</template>


<style>
.carousel__item {
    height: auto;
    width: 100%;
    object-fit: cover;
    aspect-ratio: 3/2;
    filter: grayscale(100%);
    background-color: rgb(3, 7, 18);
}

.carousel__slide {
    padding: 5px;
}

.carousel__prev,
.carousel__next {
    background-color: rgb(239, 68, 68);
    transition: .2s ease;
}

.carousel__prev:hover,
.carousel__next:hover {
    color: #fff;
}

.carousel__slide--active {
    border: 2px solid rgb(239, 68, 68);
}

.carousel__slide--active img {
    filter: grayscale(0%);
}

.carousel__pagination-button::after {
    background-color: rgb(3, 7, 18);
}

.carousel__pagination-button:hover::after,
.carousel__pagination-button--active::after {
    background-color: rgb(239, 68, 68);
}
</style>