<template>
    <div class="bg-[url('./assets/hero.png')] bg-no-repeat bg-cover bg-[bottom_2rem] md:bg-right min-h-[300px] md:min-h-[60vh] relative">
        <div class=" max-w-[1200px] m-auto">
            <div class="max-w-[1200px] bg-gradient-to-b md:bg-gradient-to-r from-gray-950 from-40% md:from-30% to-80% md:to-60% absolute w-full top-0 bottom-0 flex flex-col justify-center items-center md:items-start px-4">
                <h1 class="text-center md:text-left">
                    Jiu Jitsu in Euskirchen
                </h1>
                <p class="big-red-text text-center md:text-left">Budo Club Shogun Euskirchen e.V.</p>
                <button class="btn justify-self-start">Starte Dein kostenloses Probetraining
                    <Icon icon="maki:arrow" color="white" />
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
import { Icon } from '@iconify/vue';
</script>

<style  scoped>

</style>