<script setup>
import { RouterLink } from 'vue-router';
</script>
                
<template>
    <footer class="relative bottom-0 max-w-7xl w-full left-1/2 transform -translate-x-1/2 mb-4 px-4 pt-8">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 mb-10 relative">
            <div class="flex-col columns-1 mt-4 mb-8 sm:my-0 sm:text-sm break-inside-avoid-column lg:col-span-2">
                <p class="md-red-text">Adresse:</p>
                <p class="font-semibold">Paul-Gerhardt Schule</p>
                <p>Billiger Straße 2</p>
                <p>53879 Euskirchen</p>
                <p class="md-red-text mt-2">Kontakt:</p>
                <p>0172/2627062</p>
                <p>trainer(at)shogun-euskirchen.de</p>
            </div>
            <div class="">
                <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2529.5271029623746!2d6.784538777079904!3d50.65447317163185!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47bf10243eb77999%3A0xc0d24384b68409b7!2sBilliger%20Str.%202%2C%2053879%20Euskirchen!5e0!3m2!1sde!2sde!4v1700032219651!5m2!1sde!2sde"
                    style="border:0;" allowfullscreen="" loading="lazy" class="w-full"
                    referrerpolicy="no-referrer-when-downgrade">
                </iframe>
            </div>
        </div>
        <div class="columns-1 md:columns-2 text-sm md:text-xs">
            <nav>
                <ul class="flex items-center gap-2 justify-center md:justify-start mb-4">
                    <RouterLink to="/impressum" class="transition duration-300 hover:text-red-500">Impressum</RouterLink>
                    <div class="vertical-divider"></div>
                    <RouterLink to="/datenschutz" class="transition duration-300 hover:text-red-500">Datenschutz
                    </RouterLink>
                </ul>
            </nav>
            <p class="md:float-right text-center">Copyright © 2023 Budo Club Shogun Euskirchen e.V. </p>
        </div>
    </footer>
</template>


<style scoped>
.vertical-divider {
    background: rgb(239 68 68);
    width: 2px;
    height: 1em;
}

.router-link-exact-active {
    color: rgb(239 68 68);
}

.full-height {
    min-height: 100%;
    min-height: 100%;
}
</style>