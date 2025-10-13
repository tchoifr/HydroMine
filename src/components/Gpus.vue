<template>
  <section class="cards" id="gpu">
    <h2>Nos cartes graphiques premium</h2>
    <p style="margin-bottom: 40px;">
      Nous utilisons les meilleures cartes graphiques du moment pour garantir un
      minage performant et éco-responsable.
    </p>
    <div class="cards-grid">
      <div v-for="gpu in gpus" :key="gpu.name" class="card">
        <img :src="gpu.image" :alt="gpu.name" />
        <h3>{{ gpu.name }}</h3>
        <p class="description">{{ gpu.description }}</p>
        <p class="price">Hashrate : {{ gpu.hashrate }} MH/s</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  gpus: Array
});
</script>
