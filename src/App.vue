<script setup>
import Header from './components/Header.vue';
import Cards from './components/Cards.vue';
import Engagement from './components/Engagement.vue';
import GPU from './components/Gpus.vue';
import Footer from './components/Footer.vue';
import '../src/style.css';

// 🖼️ Import images from src/assets
import panda1 from '/public/assets/1an.png';
import panda2 from '/public/assets/2ans.png';
import panda3 from '/public/assets/3ans.png';

// 💰 Cards data with images
const cards = [
  {
    name: "Paulownia Pack - 1 Year",
    image: panda1,
    description:
      "Grow your first Paulownia 🌱 This pack allows you to take part in the cultivation of a Paulownia tree for one year. When your tree is resold, you’ll receive an estimated crypto income of around €300. A simple and eco-friendly way to make your investment grow while supporting a sustainable project.",
    price: 150,
  },
  {
    name: "Paulownia Pack - 2 Years",
    image: panda2,
    description:
      "Grow your forest 🌿 With the 2-year pack, your Paulownia grows stronger and generates an estimated crypto income of around €750 upon resale. The perfect option for those seeking a more stable, long-term return while contributing to the growth of the Paulownia ecosystem.",
    price: 280,
  },
  {
    name: "Paulownia Pack - 3 Years",
    image: panda3,
    description:
      "Become a guardian of a flourishing Paulownia 🌸 By choosing the 3-year pack, you enjoy your tree’s full maturity. Upon resale, the estimated crypto income reaches around €1,200. A sustainable, symbolic, and rewarding investment for lovers of nature and technology alike.",
    price: 400,
  },
];

// ⚙️ GPU / ecosystem data
const gpus = [
  {
    name: "Flexible Staking",
    image: "/public/assets/1.png",
    description:
      "Enjoy flexible staking — deposit or withdraw your Paulownia tokens anytime. Your assets continue generating rewards even during network rest periods.",
    apr: "8 to 12% / year",
    badge: "Flexibility",
  },
  {
    name: "Locked Staking",
    image: "/public/assets/2.png",
    description:
      "Lock your Paulownia tokens for 1, 2, or 3 years and benefit from boosted rates. The longer your commitment, the higher your returns.",
    apr: "up to 18% / year",
    badge: "Performance",
  },
  {
    name: "Community Staking",
    image: "/public/assets/3.png",
    description:
      "Join collective staking — every member strengthens the Paulownia pool. Together, we multiply the network’s value and stability.",
    apr: "varies by pool",
    badge: "Community",
  },
  {
    name: "Reinvested Revenues",
    image: "/public/assets/4.png",
    description:
      "100% of our revenue is reinvested into the Paulownia crypto. No external dividends — all value stays within the ecosystem.",
    impact: "Organic & sustainable growth",
    badge: "Transparency",
  },
  {
    name: "Our Paulownia NFTs",
    image: "/public/assets/5.png",
    description:
      "Each Paulownia NFT represents a living tree on the blockchain 🌿. It generates crypto income and evolves over time.",
    type: "Utility & evolving NFTs",
    badge: "Eco-Collection",
  },
];
</script>

<template>
  <div class="page">
    <Header />
    <Cards :cards="cards" />
    <Engagement />
    <GPU :gpus="gpus" />
    <Footer />
  </div>
</template>
