<template>
  <section class="Form" id="contact">
    <div class="Form-content">
      <h2>Contactez-nous 💬</h2>
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Nom complet</label>
          <input type="text" id="name" v-model="form.name" required />
        </div>

        <div class="form-group">
          <label for="email">Adresse email</label>
          <input type="email" id="email" v-model="form.email" required />
        </div>

        <div class="form-group">
          <label for="subject">Sujet</label>
          <input type="text" id="subject" v-model="form.subject" required />
        </div>

        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" v-model="form.message" rows="5" required></textarea>
        </div>

        <button type="submit" class="btn-login">Envoyer</button>
      </form>
    </div>
  </section>
</template>

<script setup>
import { reactive } from "vue";

const form = reactive({
  name: "",
  email: "",
  subject: "",
  message: ""
});

function submitForm() {
  console.log("Formulaire envoyé :", form);
  alert("Merci pour votre message, nous vous répondrons bientôt !");
  form.name = "";
  form.email = "";
  form.subject = "";
  form.message = "";
}
</script>

