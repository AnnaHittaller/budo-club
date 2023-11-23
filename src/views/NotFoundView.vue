<template>
    <section>
        <div>
            <h2>Error 404:
                <br>
                Diese Seite ist unerreichbar
            </h2>
            <RouterLink to="/">
                <button class="btn">Zurück zu Home</button>
            </RouterLink>
        </div>
    </section>
</template>

<script setup>
import { RouterLink } from 'vue-router';
</script>

<style lang="scss" scoped></style>