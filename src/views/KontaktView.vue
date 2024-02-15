<script setup>
import axios from 'axios'
import { ref } from 'vue';
let nachricht = {
    name: '',
    email: '',
    text: '',
}
const toast = ref(null)

const handleSubmit = async () => {
    //console.log("submitted")
    
    try {
        const response = await axios.post("https://formspree.io/f/mleykoqo", nachricht)
        //console.log(nachricht, response)
        toast.value = "Danke, deine Nachricht wurde gesendet!"

        nachricht = {
            name: '',
            email: '',
            text: '',
        }

    } catch (error) {
        console.log('Error submitting form:', error.message)
        toast.value = error.message
    } finally {
        // Ensure the toast is reset after a certain time
        setTimeout(() => {
            toast.value = null;
        }, 3000);
    }
}
</script>

<template>
    <section class="bg-white text-gray-950">
        <div class="flex flex-col justify-center items-center">
            <h2>Kontakt</h2>
            <!-- ... -->
            <form id="contact-form" name="simple-contact-form" action="https://formspree.io/f/mleykoqo" method="post"
                @submit.prevent="handleSubmit" class="w-full mt-8 max-w-xl">
                <fieldset class="flex flex-col justify-center w-full m-auto gap-4">
                    <label for="name">Name
                        <input type="text" name="name" id="name" placeholder="Deine Name" required v-model="nachricht.name">
                    </label>
                    <label for="email-address">E-Mail Addresse
                        <input type="email" name="_replyto" id="email-address" placeholder="email@domain.de" required
                            v-model="nachricht.email">
                    </label>
                    <label for="message">Nachricht
                        <textarea rows="5" name="message" id="message" placeholder="Deine Nachricht" required
                            v-model="nachricht.text"></textarea>
                    </label>
                    <input type="hidden" name="_subject" id="email-subject"
                        value="Nachricht durch der Kontaktformular der Webseite">
                </fieldset>
                <p class="w-full text-red-500 font-bold mt-4" v-if="toast !== null">{{ toast }}</p>
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

input:focus,
textarea:focus {
    border-color: rgb(239 68 68);
}

label {
    color: rgb(239 68 68);
    font-weight: 700;
}
</style>