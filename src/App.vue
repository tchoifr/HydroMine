<script setup>
import Header from './components/Header.vue';
import Cards from './components/Cards.vue';
import Engagement from './components/Engagement.vue';
import GPU from './components/Gpus.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
import '../src/style.css';

const cards = [ { name: "Offre Éco-Lite", image: "/public/assets/bronze.png", description: "Idéale pour débuter le minage durablement. Rendement estimé : 15%/mois, durée optimale : 1 mois, faible consommation d'énergie. Cette offre utilise la carte graphique NVIDIA RTX 3060 Ti, la moins puissante des 5.", price: 50, }, { name: "Offre Hydro-Pro", image: "/public/assets/fer.png", description: "Puissance doublée pour un rendement optimal. Rendement estimé : 18%/mois, durée optimale : 1-3 mois, consommation modérée. Cette offre utilise la carte graphique AMD Radeon RX 6700 XT.", price: 100, }, { name: "Offre Green-Titan", image: "/public/assets/gold.png", description: "Pour les investisseurs sérieux. Rendement estimé : 20%/mois, durée optimale : 3-6 mois, consommation élevée, performance maximale. Cette offre utilise la carte graphique NVIDIA RTX 4070 Ti.", price: 250, }, { name: "Offre Platinum", image: "/public/assets/platine.png", description: "Carte premium pour rentabilité maximale. Rendement estimé : 22%/mois, durée optimale : 6-12 mois, puissance élevée, support dédié. Cette offre utilise la carte graphique AMD Radeon RX 7900 XT.", price: 500, }, { name: "Offre Ultime", image: "/public/assets/titane.png", description: "L’offre ultime pour investisseurs ambitieux. Rendement estimé : 25%/mois, durée optimale : 12+ mois, performance maximale, assistance VIP et suivi personnalisé. Cette offre utilise la carte graphique NVIDIA RTX 4090.", price: 1000, } ];

const gpus = [{ name: "NVIDIA RTX 3060 Ti", image: "/public/assets/NVIDIARTX3060Ti.webp", description: "La NVIDIA RTX 3060 Ti est parfaite pour débuter le minage de façon durable. Faible consommation et rendement stable vous permettent de générer vos premiers gains avec sérénité.", hashrate: 60, badge: "Bronze" }, { name: "AMD Radeon RX 6700 XT", image: "/public/assets/AMDRadeonRX6700XT.jpg", description: "La AMD Radeon RX 6700 XT offre une puissance doublée pour un rendement optimal. Idéale pour les mineurs qui veulent passer à la vitesse supérieure tout en maîtrisant la consommation.", hashrate: 85, badge: "Fer" }, { name: "NVIDIA RTX 4070 Ti", image: "/public/assets/NVIDIARTX4070Ti.jpg", description: "La NVIDIA RTX 4070 Ti est conçue pour les investisseurs sérieux. Performance élevée et stabilité maximale pour un rendement fiable sur le long terme.", hashrate: 100, badge: "Gold" }, { name: "AMD Radeon RX 7900 XT", image: "/public/assets/AMDRadeonRX7900XT.png", description: "La AMD Radeon RX 7900 XT est une carte premium, offrant une rentabilité maximale et une puissance exceptionnelle. Idéale pour les mineurs ambitieux cherchant performance et endurance.", hashrate: 120, badge: "Platine" }, { name: "NVIDIA RTX 4090", image: "/public/assets/NVIDIARTX4090.webp", description: "La NVIDIA RTX 4090 représente l’ultime choix pour les investisseurs exigeants. Performance inégalée, support VIP et suivi personnalisé pour maximiser vos profits.", hashrate: 130, badge: "Supreme" }];
</script>

<template>
  <div class="page">
    <Header />
    <Cards :cards="cards" />
    <Engagement />
    <GPU :gpus="gpus" />
    <Contact />
    <Footer />
  </div>
</template>