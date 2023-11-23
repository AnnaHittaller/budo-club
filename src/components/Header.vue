<script setup>
import { RouterLink, useRouter } from 'vue-router';
import { Icon } from '@iconify/vue';
import { ref, watchEffect } from 'vue';

const route = useRouter()
const path = ref(route.currentRoute.value.name);
const isHome = ref(false);

watchEffect(() => {
    path.value = route.currentRoute.value.name;
    isHome.value = path.value === 'home';
    //console.log(path.value);
    //console.log(isHome.value); 
})

let isMenuOpen = ref(false)

const toggleMobileMenu = () => {
    isMenuOpen.value = !isMenuOpen.value

    const closeMenu = () => {
        isMenuOpen.value = false
        window.removeEventListener('click', closeMenu);
    }

    window.addEventListener("click", closeMenu)

    if (isMenuOpen.value === true) {
        window.addEventListener("click", closeMenu)
    } else {
        window.removeEventListener("click", closeMenu)
    }
}

</script>

<template>
    <header class="w-full" :class="isHome ? 'absolute' : 'static'">
        <nav class="flex justify-between items-center py-4 px-4 max-w-[1400px] m-auto h-min relative">
            <ul class="flex md:justify-start gap-4 items-center  max-md:absolute max-md:top-[100%] max-md:translate-y-[0] max-md:left-0 max-md:right-0 max-md:flex-col max-md:bg-gray-950 max-md:py-10 max-md:z-10 max-md:border-b-2 max-md:border-red-500 max-md:shadow-lg max-md:text-2xl"
                :class="isMenuOpen ? '' : 'out-of-screen'">
                <RouterLink to="/kontakt">
                    <button class="btn-outline">Kontakt</button>
                </RouterLink>
                <RouterLink to="/" class=" group transition duration-300 ">Home
                    <span class="underline-span"></span>
                </RouterLink>
                <div class="vertical-divider max-md:hidden"></div>
                <RouterLink to="/about" class=" group transition  duration-300 ">Über uns<span
                        class="underline-span"></span></RouterLink>
                        <div class="vertical-divider max-md:hidden"></div>
                    <RouterLink to="/jiu-jitsu" class=" group transition  duration-300 ">Jiu Jitsu<span
                            class="underline-span"></span></RouterLink>
                <div class="vertical-divider max-md:hidden"></div>
                <RouterLink to="/training" class=" group transition  duration-300 ">Training<span
                        class="underline-span"></span></RouterLink>
                <!-- <div class="vertical-divider max-md:hidden"></div>
                <RouterLink to="/" class=" group transition  duration-300 ">Training Jugendliche und Erwachsene<span
                        class="underline-span"></span></RouterLink> -->
        
            </ul>
            <RouterLink to="/" class="max-md:h-16"><img src="../assets/logo_small.png" alt="logo" class="h-full">
            </RouterLink>
            <div class="hamburger md:hidden flex items-center justify-center" @click.stop="toggleMobileMenu">
                <Icon icon="game-icons:hamburger-menu" color="rgb(239 68 68)" width="30"
                    class="transition duration-200 hover:scale-125 cursor-pointer" :class="{ hidden: isMenuOpen }" />
                <Icon icon="vaadin:close" color="rgb(239 68 68)" width="25" height="25"
                    class="transition duration-200 hover:scale-125 cursor-pointer" :class="{ hidden: !isMenuOpen }" />
            </div>
        </nav>
    </header>
</template>


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

.icon {
    width: 100%;
}


@media screen and (max-width: 768px) {

    .out-of-screen {
        transform: translateY(-500%);
    }

}
</style>