<script setup>
import Hero from '../components/Hero.vue';
import { RouterLink } from 'vue-router';
import Card from '../components/Card.vue';
</script>

<template>
  <main class="relative">
    <Hero />
    <section class="bg-white">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 content-center justify-center">
        <img src="../assets/logo-big.gif" alt="Budo Club Shogun Logo" class=" max-w-[150px] md:max-w-[200px] m-auto">
        <div class="md:col-span-2">
          <p class="md-red-text">Willkommen bei dem Budo Club Shogun - wo Leidenschaft, Energie und Teamgeist
            aufeinandertreffen</p>
          <p class="text-gray-950 font-medium my-4 md:text-sm">Egal ob groß oder klein, wir heißen alle herzlich
            willkommen, die sich für diese mitreißende Sportart
            begeistern. Jiu Jitsu ist nicht nur ein Workout, sondern ein Lebensstil, der Körper und Geist gleichermaßen
            stärkt. Unsere hochqualifizierten Trainer sind hier, um Dir die Grundlagen beizubringen und Dein Können auf
            ein neues Level zu katapultieren! Werde Teil unserer Jiu Jitsu-Familie und erlebe die unvergleichliche
            Begeisterung dieses Sports! Trete noch heute bei und entdecke, wie Jiu Jitsu Dein Leben verändern kann!</p>
          <RouterLink to="/about">
            <button class="btn mt-8 m-auto md:ml-0">Mehr über uns</button>
          </RouterLink>
        </div>
      </div>
    </section>
    <section>
      <div>

        <h2 class="text-center">Du hast Lust Jiu Jitsu zu lernen?</h2>
        <p class="md:text-sm text-center">Bei uns ist der Einstieg jederzeit möglich.
          Du brauchst keine Vorkenntnisse und trägst am besten bequeme Sportkleidung.
          Wir freuen uns auf Dich!</p>
        <div
          class="grid grid-cols-1 gap-6 justify-items-center justify-center pt-10 sm:grid-cols-2 md:grid-cols-3 md:text-sm">
          <Card title="Für Jugendliche und Erwachsene"
            text="Für Erwachsene ist Jiu Jitsu eine kraftvolle Möglichkeit, Stress abzubauen und sich in Topform zu bringen."
            img="Training.png" />
          <Card title="Für Kinder ab 6"
            text="Für Kinder ab 6 Jahren bieten wir spezielle Kurse an, die ihre Energie kanalisieren und ihr Selbstbewusstsein stärken."
            img="Kindertraining.png" />
          <Card title="Kostenloses Probetraining"
            text="Kommen Sie vorbei und sichern Sie sich ein kostenloses Probetraining, um einen Einblick in unsere vielfältigen Trainingsangebote zu erhalten!"
            img="Probetraining.png" />
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
/* main {
  max-width: 1200px;
  margin: 0 auto;
  border: 1px solid red;
} */
</style>