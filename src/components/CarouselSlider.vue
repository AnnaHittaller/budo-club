<script setup>
import { ref } from 'vue'

import { register } from 'swiper/element/bundle';
register();
import 'swiper/css/bundle';

// const onProgress = (e) => {
//     const [swiper, progress] = e.detail;
//     console.log(progress, swiper)
// };

// const onSlideChange = (e) => {
//     console.log('slide changed', e)
// }

const thumbsSwiper = ref(null);

const setThumbsSwiper = (swiper) => {
    thumbsSwiper.value = swiper;
};

const breakpoints = {
    640: {
        slidesPerView: 2,
    },
    1024: {
        slidesPerView: 3
    }
}

</script>

<template>
    <swiper-container id="my-Slider" thumbs-swiper="#my-thumbs" :slides-per-view="1" :space-between="10"
        :centered-slides="true" :loop="false" :navigation="true" :pagination="{
            clickable: true,
        }" :breakpoints="breakpoints"
        keyboard="{enabled: true}" grab-cursor="true">
        <swiper-slide class=" swiper-slide"><img src="../assets/Probetraining.png" /></swiper-slide>
        <swiper-slide class="swiper-slide"><img src="../assets/Kindertraining.png" /></swiper-slide>
        <swiper-slide class="swiper-slide"><img src="../assets/Training.png" /></swiper-slide>
        <swiper-slide class="swiper-slide"><img src="../assets/Kindertraining.png" /></swiper-slide>
        <swiper-slide class="swiper-slide"><img src="../assets/Probetraining.png" /></swiper-slide>
        <swiper-slide class="swiper-slide"><img src="../assets/Training.png" /></swiper-slide>
    </swiper-container>

    <swiper-container id="my-thumbs" @swiper="setThumbsSwiper" :loop="false" :spaceBetween="10" :slidesPerView="4"
        :watchSlidesProgress="true" auto-scroll-offset="1">
        <swiper-slide><img src="../assets/Probetraining.png" /></swiper-slide>
        <swiper-slide><img src="../assets/Kindertraining.png" /></swiper-slide>
        <swiper-slide><img src="../assets/Training.png" /></swiper-slide>
        <swiper-slide><img src="../assets/Kindertraining.png" /></swiper-slide>
        <swiper-slide><img src="../assets/Probetraining.png" /></swiper-slide>
        <swiper-slide><img src="../assets/Training.png" /></swiper-slide>
    </swiper-container>
</template>


<style>
swiper-container::part(bullet-active) {
    background-color: rgb(239, 68, 68);
}

swiper-container::part(button-next),
swiper-container::part(button-prev) {
    height: 2.5rem;
    padding: .5rem .25rem;
    background-color: rgb(239, 68, 68);
}

#my-Slider {
    --swiper-theme-color: white;
}

.swiper-slide {
    display: flex;
    justify-content: center;
    align-items: center;
}

#my-Slider .swiper-slide img,
#my-Slider .swiper-slide img {
    filter: grayscale(1)
}

#my-Slider .swiper-slide-active img {
    filter: grayscale(0);
    border: 2px solid rgb(239, 68, 68);
}

#my-thumbs .swiper-slide-thumb-active img {
    opacity: 1;
    filter: grayscale(0);
    border: 2px solid rgb(239, 68, 68);
}

#my-thumbs {
    height: 20%;
    box-sizing: border-box;
    padding: 10px 0;
}

#my-thumbs img {
    max-height: 100px;
    opacity: .5;
    height: 100%;
    width: 100%;
    object-fit: cover;
    filter: grayscale(1);
}

#my-thumbs .swiper-slide {
    width: 25%;
    height: 100%;
    object-fit: cover;
    opacity: 0.4;
}

#my-thumbs .swiper-slide img {
    height: 100%;
    max-height: 150px;

}




/* .carousel__item {
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
} */
</style>