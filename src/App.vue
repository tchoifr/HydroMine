<script setup>
import Header from './components/Header.vue';
import Cards from './components/Cards.vue';
import Engagement from './components/Engagement.vue';
import GPU from './components/Gpus.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
import '../src/style.css';

// 🖼️ Import des images depuis src/assets
import panda1 from '/public/assets/panda1an.jpg';
import panda2 from '/public/assets/panda2ans.jpg';
import panda3 from '/public/assets/panda3ans.jpg';


import NVIDIARTX3060Ti from '/public/assets/NVIDIARTX3060Ti.webp';
import AMDRadeonRX6700XT from '/public/assets/AMDRadeonRX6700XT.jpg';
import NVIDIARTX4070Ti from '/public/assets/NVIDIARTX4070Ti.jpg';
import AMDRadeonRX7900XT from '/public/assets/AMDRadeonRX7900XT.png';
import NVIDIARTX4090 from '/public/assets/NVIDIARTX4090.webp';

// 💰 Tes données avec les imports d’images
const cards = [
  {
    name: "Pack Palmonia 1 an",
    image: panda1,
    description:
      "Fais pousser ton premier Palmonia 🌱 Ce pack te permet de participer à la culture d’un arbre Palmonia pendant 1 an. À la revente de ton arbre, tu reçois une rente crypto estimée à environ 300 €. Un moyen simple et vert de faire fructifier ton investissement tout en soutenant un projet durable.",
    price: 150,
  },
  {
    name: "Pack Palmonia 2 ans",
    image: panda2,
    description:
      "Fais grandir ta forêt 🌿 Avec le pack 2 ans, ton Palmonia se développe davantage et génère une rente crypto estimée à environ 750 € lors de la revente. Une option parfaite pour ceux qui veulent un rendement plus stable sur le long terme tout en participant à la croissance de l’écosystème Palmonia.",
    price: 280,
  },
  {
    name: "Pack Palmonia 3 ans",
    image: panda3,
    description:
      "Deviens gardien d’un Palmonia florissant 🌸 En choisissant le pack 3 ans, tu profites de la pleine maturité de ton arbre. À la revente, la rente crypto estimée atteint environ 1 200 €. Un investissement durable, symbolique et rémunérateur pour les amoureux de nature et de technologie.",
    price: 400,
  },
];


const gpus = [
  {
    name: "Staking flexible",
    image: "/public/assets/1.png",
    description:
      "Profite d’un staking souple : retire ou ajoute tes PALMONIA à tout moment. Tes tokens continuent de générer des rendements même pendant les périodes de repos du réseau.",
    apr: "8 à 12% / an",
    badge: "Souplesse",
  },
  {
    name: "Staking bloqué",
    image: "/public/assets/2.png",
    description:
      "Verrouille tes PALMONIA pour 3, 6 ou 12 mois et bénéficie de taux bonifiés. Plus tu t’engages, plus ton rendement augmente.",
    apr: "jusqu’à 18% / an",
    badge: "Performance",
  },
  {
    name: "Staking communautaire",
    image: "/public/assets/3.png",
    description:
      "Participe au staking collectif : chaque membre renforce la pool PALMONIA. Ensemble, nous multiplions la valeur et la stabilité du réseau.",
    apr: "variable selon la pool",
    badge: "Communauté",
  },
  {
    name: "Revenus réinvestis",
    image: "/public/assets/4.png",
    description:
      "100% du chiffre d’affaires est réinjecté dans notre crypto PALMONIA. Aucun dividende externe — toute la valeur circule dans l’écosystème.",
    impact: "Croissance organique & durable",
    badge: "Transparence",
  },
  {
    name: "Nos NFT Palmonia",
    image: "/public/assets/5.png",
    description:
      "Chaque NFT Palmonia représente un arbre vivant sur la blockchain 🌿. Il génère une rente en crypto et évolue au fil du temps.",
    type: "NFT utilitaires & évolutifs",
    badge: "Éco-collection",
  },
];

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