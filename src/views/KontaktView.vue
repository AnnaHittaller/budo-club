<script setup>
const handleSubmit = () => {
    console.log("submitted")
    // import axios, send form through it, add a reactive toast and dislay it with v-if
}
</script>

<template>
    <section class="bg-white text-gray-950">

        <div class="flex flex-col justify-center items-center">
            <h2>Kontakt</h2>
            <p class="text-center max-w-[800px]">Du möchtest Dich zu einem kostenlosen und unverbindlichen Probetraining anmelden oder
                hast noch offene
                Fragen?
                <br>
                Dann sende gern eine Nachricht hier oder eine E-Mail an: trainer(at)shogun-euskirchen.de
                oder melde Dich telefonisch unter: 0172 / 2627062.
                <br>
                Bitte verwende nicht die Adresse unseres Dojos um Kontakt zu uns aufzunehmen.
            </p>
            <form id="contact-form" name="simple-contact-form" action="https://formspree.io/f/mleykoqo" method="post" @submit.prevent="handleSubmit"
                class="w-full mt-8 max-w-xl">
                <fieldset class="flex flex-col justify-center w-full m-auto gap-4">
                    <label for="name">Name

                        <input type="text" name="name" id="name" placeholder="Deine Name" required="true">
                    </label>
                    <label for="email-address">E-Mail Addresse

                        <input type="email" name="_replyto" id="email-address" placeholder="email@domain.de"
                            required="true">
                    </label>
                    <label for="message">Nachricht

                        <textarea rows="5" name="message" id="message" placeholder="Deine Nachricht"
                            required="true"></textarea>
                    </label>
                    <input type="hidden" name="_subject" id="email-subject"
                        value="Nachricht durch der Kontaktformular der Webseite">
                </fieldset>
                <button type="submit" class="btn max-md:ml-[50%] max-md:translate-x-[-50%]">Nachricht senden</button>
            </form>
        </div>
    </section>
</template>


<style scoped>
input,
textarea {
    border: 2px solid rgb(3, 7, 18);
    padding: .25rem .5rem;
    width: 100%;
    margin-top: 1rem;
    color: rgb(3, 7, 18);
    font-weight: 500;
    outline: none;
}

input:focus, textarea:focus {
    border-color: rgb(239 68 68);
}

label {
    color: rgb(239 68 68);
    font-weight: 700;
}
</style>