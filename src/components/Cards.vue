<template>
  <section class="cards" id="cards">
    <h2>Nos Offres de Minage</h2>
    <div class="cards-grid">
      <div v-for="card in cards" :key="card.name" class="card">
        <img :src="card.image" :alt="card.name" />
        <h3>{{ card.name }}</h3>
        <p class="description">{{ card.description }}</p>
        <p class="price">{{ card.price }} €</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  cards: Array
});
</script>
