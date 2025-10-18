<template>
<section class="cards" id="gpu">
  <h2>Our Sustainable Crypto Ecosystem 🌿</h2>
  <p style="margin-bottom: 40px; color: white;">
    Discover how <strong>Panda Paulownia</strong> unites nature and blockchain through an ethical and transparent system:  
    smart staking, full revenue reinvestment, and living NFTs connected to green growth.
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
