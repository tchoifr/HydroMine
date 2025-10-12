<template>
  <section class="contact" id="contact">
    <h2>Contactez-nous</h2>
    <form @submit.prevent="submitForm">
      <input type="text" v-model="form.name" placeholder="Nom" required />
      <input type="email" v-model="form.email" placeholder="Email" required />
      <textarea v-model="form.message" placeholder="Votre message" required></textarea>
      <button type="submit">Envoyer</button>
    </form>
    <p v-if="formSubmitted" class="success">Merci ! Votre message a été envoyé.</p>
  </section>
</template>

<script setup>
import { ref } from "vue";

const form = ref({ name: "", email: "", message: "" });
const formSubmitted = ref(false);

function submitForm() {
  console.log("Form submitted:", form.value);
  formSubmitted.value = true;
  form.value = { name: "", email: "", message: "" };
}
</script>
