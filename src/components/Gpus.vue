<template>
  <section class="cards" id="gpu">
<h2>Notre écosystème crypto durable 🌿</h2>
<p style="margin-bottom: 40px; color: white;">
  Découvrez comment <strong>Panda Palmonia</strong> unit la nature et la blockchain à travers un système éthique et transparent :  
  staking intelligent, réinvestissement total des revenus et NFT vivants connectés à la croissance verte.
</p>

    <div class="cards-grid">
      <div v-for="gpu in gpus" :key="gpu.name" class="card">
        <img :src="gpu.image" :alt="gpu.name" />
        <h3>{{ gpu.name }}</h3>
        <p class="description">{{ gpu.description }}</p>
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
