<script setup>
import { Icon } from '@iconify/vue';
</script>

<template>
    <div
        class="bg-[url('./assets/hero.png')] bg-cover bg-[bottom_2rem] sm:bg-center h-max min-h-[300px] md:min-h-[400px] lg:min-h-[500px] relative">
        <div
            class="w-full m-auto bg-gradient-to-b md:bg-gradient-to-r from-gray-950 from-40% md:from-30% to-80% md:to-70% absolute top-0 bottom-0 flex items-center justify-center ">
            <div class="flex flex-col justify-center items-center md:items-start px-4 w-full max-w-7xl md:pt-20 ">
                <h1 class="text-center md:text-left">
                    Jiu Jitsu in Euskirchen
                </h1>
                <p class="big-red-text text-center md:text-left">Budo Club Shogun Euskirchen e.V.</p>
                <RouterLink to="/kontakt">
                    <button class="btn justify-self-start">Starte Dein kostenloses Probetraining
                        <Icon icon="maki:arrow" color="white" />
                    </button>
                </RouterLink>
            </div>
        </div>
    </div>
</template>


<style  scoped></style>