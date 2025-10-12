<template>
  <section class="gpu" id="gpu">
    <h2>Nos cartes graphiques premium</h2>
    <p>Nous utilisons les meilleures cartes graphiques du moment pour garantir un minage performant et éco-responsable.</p>
    <div class="gpu-grid">
      <div class="gpu-card" v-for="gpu in gpus" :key="gpu.name">
        <img :src="gpu.image" :alt="gpu.name" />
        <h3>{{ gpu.name }}</h3>
        <p class="gpu-desc">{{ gpu.description }}</p>
        <p class="gpu-power">Hashrate : {{ gpu.hashrate }} MH/s</p>
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
