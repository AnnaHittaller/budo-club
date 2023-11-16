<template>
    <Carousel :breakpoints="breakpoints" :wrap-around="false" class="px-10">
        <Slide v-for="slide in slides" :key="slide.id">
            <!-- <div class="carousel__item"> -->
            <img :src="slide.imageSrc" alt="Budo Club Shogun Euskirchen Training" class="carousel__item" />
            <!-- <h3>{{ slide.title }}</h3>
                <p>{{ slide.content }}</p> -->
            <!-- </div> -->
        </Slide>

        <template #addons>
            <Navigation />
            <Pagination />
        </template>
    </Carousel>
</template>

<script setup>
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'


const slides = [
    { id: '1', title: 'Vue 3 Introduction', content: 'VueJS is a library', path: 'hero.png' },
    { id: '2', title: 'Vue 3 Components', content: 'Know the components', path: 'Training.png' },
    { id: '3', title: 'Vue 3 Conditional', content: 'Rendering Conditionally', path: 'Kindertraining.png' },
    { id: '4', title: 'Vue 3 Reactivity', content: 'VueJS is Reactive', path: 'Probetraining.png' },
    { id: '5', title: 'Vue 3 Compute', content: 'VueJS uses computed properties', path: 'hero.png' },
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
            console.log('Image loaded for slide', slide.id)
        }
    } catch (error) {
        console.error(error);
    }
};

requireImages();

</script>

<style>
.carousel__item {
    height: auto;
    width: 100%;
    object-fit: cover;
    aspect-ratio: 3/2;
    filter: grayscale(100%);
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