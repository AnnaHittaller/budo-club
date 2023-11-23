<script setup>
import Hero from '../components/Hero.vue';
import { RouterLink } from 'vue-router';
import Card from '../components/Card.vue';
import CarouselSlider from '../components/CarouselSlider.vue';
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
            img="Training.png" buttonLink="#training" />
          <Card title="Für Kinder ab 6"
            text="Für Kinder ab 6 Jahren bieten wir spezielle Kurse an, die ihre Energie kanalisieren und ihr Selbstbewusstsein stärken."
            img="Kindertraining.png" buttonLink="#kindertraining" />
          <Card title="Kostenloses Probetraining"
            text="Komm vorbei und sichere Dich ein kostenloses Probetraining, um einen Einblick in unsere vielfältigen Trainingsangebote zu erhalten!"
            img="Probetraining.png" buttonLink="#probetraining" />
        </div>
      </div>
    </section>
    <section
      class="bg-[linear-gradient(180deg,_#ffffff_45%,_rgb(239,68,68)_45%)] md:bg-[linear-gradient(90deg,_#ffffff_50%,_rgb(239,68,68)_50%)] lg:bg-[linear-gradient(120deg,_#ffffff_50%,_rgb(239,68,68)_50%)]">
      <div class="columns-1 md:columns-2 lg:gap-[10vw] md:text-sm md:gap-10">
        <div class="text-gray-950 font-medium break-inside-avoid-column mb-8 md:md-0">
          <h2>Unsere Trainingszeiten</h2>
          <p class="font-bold">Kinder ab 6 Jahre:</p>
          <p>Donnerstags, 18:00-19:00 Uhr</p>
          <p class="font-bold mt-4">Jugendliche und Erwachsene:</p>
          <p>Dienstags, 19:30-21:00 UhrDonnerstags, 19:00-20:00 Uhr</p>
        </div>
        <div class="text-gray-950 font-medium break-inside-avoid-column pt-8 md:pt-0">
          <h2>Mitgliedsbeiträge</h2>
          <p class="font-bold mb-4">Unsere monatlichen Mitgliedsbeiträge:</p>
          <ul class="list-disc list-inside pl-4 mb-4">
            <li class=""><span class="font-bold">7 €</span> für Kinder bis einschließlich 11 Jahre</li>
            <li><span class="font-bold">10 €</span> für Jugendliche von 12 bis einschließlich 17 Jahre</li>
            <li><span class="font-bold">13 €</span> für Erwachsene</li>
          </ul>
          <p>Für neue Mitglieder fällt eine einmalige Aufnahmegebühr von <span class="whitespace-nowrap">15 €</span> an.
          </p>
        </div>
      </div>
    </section>
    <section>
      <div class="relative">
        <img src="../assets/jiu_jitsu_kanji.png" alt="Kanji von Jiu Jitsu"
          class="max-md:absolute max-h-[80%] max-md:top-[50%] max-md:left-[50%] max-md:translate-x-[-50%] max-md:translate-y-[-50%] max-md:-z-10 hue-rotate-[340deg] max-md:opacity-50 md:float-right md:pr-[10vw] md:max-h-[250px]">
        <h2 class="max-md:text-center">Was ist Jiu Jitsu?</h2>
        <p class="md:max-w-[800px] md:text-sm">Jiu Jitsu ist eine aus Japan stammende Kampfkunst und ist eine
          Selbstverteidigungsart, die sich ständig weiterentwickelt.
          Diese beeindruckende Disziplin ist für jeden erlernbar und erweist sich besonders für Frauen als äußerst
          effektive Technik zur Selbstverteidigung. Durch das Training werden nicht nur die körperliche Fitness und
          Beweglichkeit gesteigert, sondern es wird auch ein tieferes Gefühl der Ausgeglichenheit und inneren Stärke
          gefördert. In unserer Schule legen wir einen besonderen Fokus auf Partnerschonung und Selbstkontrolle, was
          bedeutet, dass Verletzungen grundsätzlich ausgeschlossen sind. So kannst du Dich voll und ganz auf Dein Training
          konzentrieren und Deine Fähigkeiten auf ein neues Level bringen.</p>
        <RouterLink to="/jiu-jitsu">
          <button class="btn m-auto mt-8 md:ml-0">Mehr über Jiu Jitsu</button>
        </RouterLink>
      </div>
    </section>
    <section class="bg-white">
      <div>
        <CarouselSlider />
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