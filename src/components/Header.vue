<template>
    <header class="fixed w-full">
        <nav class="flex justify-between items-center py-4 px-4 max-w-[1400px] m-auto">
            <ul class="flex justify-start gap-4 items-center">
                <RouterLink to="/kontakt">
                    <button class="btn-outline">Kontakt</button>
                </RouterLink>

                <RouterLink to="/" class=" group transition  duration-300 ">Home
                    <span class="underline-span"></span>
                </RouterLink>
                <div class="vertical-divider"></div>
                <RouterLink to="/about" class=" group transition  duration-300 ">Über uns<span
                        class="underline-span"></span></RouterLink>
                <div class="vertical-divider"></div>
                <RouterLink to="/jiu-jitsu" class=" group transition  duration-300 ">Jiu Jitsu<span
                        class="underline-span"></span></RouterLink>
            </ul>
            <RouterLink to="/"><img src="../assets/logo_small.png" alt="logo"></RouterLink>
        </nav>
    </header>
</template>

<script setup>
import { RouterLink } from 'vue-router';


</script>

<style scoped>
.router-link-exact-active {
    color: rgb(239 68 68);
}

.nav-link {
    transition: .2s ease-in-out;
}

.vertical-divider {
    background: rgb(239 68 68);
    width: 2px;
    height: 1em;
}

header {
    z-index: 10;
}
</style>