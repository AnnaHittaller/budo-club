<template>
    <footer class="absolute bottom-0 max-w-[1200px] w-full left-1/2 transform -translate-x-1/2 mb-4 ">
        <div class="columns-1 md:columns-2 gap-4 mb-10">
            <div class="flex-col columns-1 my-4 md:m-0">
                <p class="md-red-text">Adresse:</p>
                <p class="font-semibold">Paul-Gerhardt Schule</p>
                <p>Billiger Straße 2</p>
                <p>53879 Euskirchen</p>
                <p class="md-red-text mt-2">Kontakt:</p>
                <p>0172/2627062</p>
                <p>trainer(at)shogun-euskirchen.de</p>
            </div>
            <div class="w-4/5 max-w-md bg-slate-200 h-44 md:float-right m-auto">Google Map</div>
        </div>
        <div class="columns-1 md:columns-2 text-sm">
            <nav>
                <ul class="flex items-center gap-2 justify-center md:justify-start mb-4">
                    <RouterLink to="/" class="transition duration-300 hover:text-red-500">Impressum</RouterLink>
                    <div class="vertical-divider"></div>
                    <RouterLink to="/" class="transition duration-300 hover:text-red-500">Datenschutz</RouterLink>
                </ul>
            </nav>
            <p class="md:float-right text-center">Copyright (C) 2023 Budo Club Shogun Euskirchen e.V. </p>
        </div>
    </footer>
</template>

<script setup>
import { RouterLink } from 'vue-router';
</script>

<style scoped>
.vertical-divider {
    background: rgb(239 68 68);
    width: 2px;
    height: 1em;
}

.router-link-exact-active {
    /* color: rgb(239 68 68); */
}
</style>