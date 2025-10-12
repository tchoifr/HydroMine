<template>
  <div class="page">
    <!-- HEADER FULL SCREEN -->
    <header class="header">
      <!-- VIDEO DE FOND -->
      <video autoplay muted loop class="header-video">
        <source src="./assets/header.mp4" type="video/mp4" />
        Votre navigateur ne supporte pas la vidéo.
      </video>

      <!-- NAVIGATION ET CONTENU -->
      <div class="nav">
        <div class="logo">HydroMine</div>
        <nav>
          <a href="#cards">Cartes</a>
          <a href="#engagement">Engagement</a>
          <a href="#gpu">GPU</a>
          <a href="#contact">Contact</a>
        </nav>
        <button class="btn-login">Connexion</button>
      </div>

      <div class="header-content">
        <h1>HydroMine Québec</h1>
        <p>Minage éco-responsable propulsé par l’hydroélectricité</p>
        <a href="#cards" class="cta-btn">Découvrir nos cartes</a>
      </div>
    </header>

    <!-- CARTES -->
    <section class="cards" id="cards">
      <h2>Nos cartes virtuelles</h2>
      <div class="cards-grid">
        <div v-for="card in cards" :key="card.name" class="card">
                  <img :src="card.image" :alt="card.name" />
          <h3>{{ card.name }}</h3>
          <p class="description">{{ card.description }}</p>
          <p class="price">{{ card.price }} €</p>
        </div>
      </div>
    </section>

    <!-- ENGAGEMENT -->
    <section class="engagement" id="engagement">
      <h2>Un engagement éthique et rentable 🌱</h2>
      <p>
        Grâce à l’énergie hydroélectrique du Québec, HydroMine combine performance et respect de la planète.
        Chaque carte louée contribue à un avenir plus vert tout en générant un revenu passif pour nos utilisateurs.
      </p>
    </section>

  <!-- CARTES GRAPHIQUES -->
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


    <!-- CONTACT -->
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

    <!-- FOOTER FULL SCREEN -->
    <footer class="footer">
      <h2>HydroMine Québec</h2>
      <p>Minage durable et rentable alimenté à 100% par l’hydroélectricité du Québec</p>
      <p>© 2025 HydroMine Québec</p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";

const cards = [
  {
    name: "Offre Éco-Lite",
    image: "/src/assets/bronze.png",
    description: "Idéale pour débuter le minage durablement. Rendement estimé : 15%/mois, durée optimale : 1 mois, faible consommation d'énergie. Cette offre utilise la carte graphique NVIDIA RTX 3060 Ti, la moins puissante des 5.",
    price: 50,
  },
  {
    name: "Offre Hydro-Pro",
    image: "/src/assets/fer.png",
    description: "Puissance doublée pour un rendement optimal. Rendement estimé : 18%/mois, durée optimale : 1-3 mois, consommation modérée. Cette offre utilise la carte graphique AMD Radeon RX 6700 XT.",
    price: 100,
  },
  {
    name: "Offre Green-Titan",
    image: "/src/assets/gold.png",
    description: "Pour les investisseurs sérieux. Rendement estimé : 20%/mois, durée optimale : 3-6 mois, consommation élevée, performance maximale. Cette offre utilise la carte graphique NVIDIA RTX 4070 Ti.",
    price: 250,
  },
  {
    name: "Offre Platinum",
    image: "/src/assets/platine.png",
    description: "Carte premium pour rentabilité maximale. Rendement estimé : 22%/mois, durée optimale : 6-12 mois, puissance élevée, support dédié. Cette offre utilise la carte graphique AMD Radeon RX 7900 XT.",
    price: 500,
  },
  {
    name: "Offre Ultime",
    image: "/src/assets/titane.png",
    description: "L’offre ultime pour investisseurs ambitieux. Rendement estimé : 25%/mois, durée optimale : 12+ mois, performance maximale, assistance VIP et suivi personnalisé. Cette offre utilise la carte graphique NVIDIA RTX 4090.",
    price: 1000,
  }
];

const form = ref({ name: "", email: "", message: "" });
const formSubmitted = ref(false);

function submitForm() {
  console.log("Form submitted:", form.value);
  formSubmitted.value = true;
  form.value = { name: "", email: "", message: "" };
}

const gpus = [
  {
    name: "NVIDIA RTX 3060 Ti",
    image: "/src/assets/NVIDIARTX3060Ti.webp",
    description: "La NVIDIA RTX 3060 Ti est parfaite pour débuter le minage de façon durable. Faible consommation et rendement stable vous permettent de générer vos premiers gains avec sérénité.",
    hashrate: 60,
    badge: "Bronze"
  },
  {
    name: "AMD Radeon RX 6700 XT",
    image: "/src/assets/AMDRadeonRX6700XT.jpg",
    description: "La AMD Radeon RX 6700 XT offre une puissance doublée pour un rendement optimal. Idéale pour les mineurs qui veulent passer à la vitesse supérieure tout en maîtrisant la consommation.",
    hashrate: 85,
    badge: "Fer"
  },
  {
    name: "NVIDIA RTX 4070 Ti",
    image: "/src/assets/NVIDIARTX4070Ti.jpg",
    description: "La NVIDIA RTX 4070 Ti est conçue pour les investisseurs sérieux. Performance élevée et stabilité maximale pour un rendement fiable sur le long terme.",
    hashrate: 100,
    badge: "Gold"
  },
  {
    name: "AMD Radeon RX 7900 XT",
    image: "/src/assets/AMDRadeonRX7900XT.png",
    description: "La AMD Radeon RX 7900 XT est une carte premium, offrant une rentabilité maximale et une puissance exceptionnelle. Idéale pour les mineurs ambitieux cherchant performance et endurance.",
    hashrate: 120,
    badge: "Platine"
  },
  {
    name: "NVIDIA RTX 4090",
    image: "/src/assets/NVIDIARTX4090.webp",
    description: "La NVIDIA RTX 4090 représente l’ultime choix pour les investisseurs exigeants. Performance inégalée, support VIP et suivi personnalisé pour maximiser vos profits.",
    hashrate: 130,
    badge: "Supreme"
  }
];

</script>

<style>
/* ----- GLOBAL ----- */
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: 'Inter', sans-serif; color: #333; }

/* ----- HEADER FULL SCREEN ----- */
.header {
  position: relative;
  height: 100vh;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;
}
.header-video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
}
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 3rem;
  background: rgba(0,0,0,0.3);
  z-index: 2;
  position: relative;
}
.header-content {
  text-align: center;
  margin-bottom: 5rem;
  z-index: 2;
  position: relative;
}
.logo { font-size: 1.5rem; font-weight: bold; }
.nav a { color: white; margin: 0 1rem; text-decoration: none; font-weight: 500; }
.nav a:hover { text-decoration: underline; }
.btn-login {
  background: #ffdd57;
  color: #0072ff;
  border: none;
  padding: 0.5rem 1.5rem;
  border-radius: 25px;
  cursor: pointer;
  font-weight: bold;
}
.btn-login:hover { background: #ffd11a; }
.header-content h1 { font-size: 4rem; font-weight: bold; margin-bottom: 1rem; text-shadow: 2px 2px 8px rgba(0,0,0,0.5); }
.header-content p { font-size: 1.5rem; margin-bottom: 2rem; text-shadow: 1px 1px 6px rgba(0,0,0,0.5); }
.cta-btn {
  background: #ffdd57;
  color: #0072ff;
  padding: 0.8rem 2rem;
  border-radius: 30px;
  font-weight: bold;
  text-decoration: none;
  cursor: pointer;
}
.cta-btn:hover { background: #ffd11a; }

/* ----- CARTES ----- */
.cards { padding: 3rem 1rem; text-align: center; background: #f0f9ff; }
.cards h2 { font-size: 2rem; margin-bottom: 2rem; color: #0072ff; }
.cards-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 2rem; }
.card { position: relative; background: white; border-radius: 20px; padding: 1.5rem; box-shadow: 0 4px 15px rgba(0,0,0,0.1); transition: 0.3s; }
.card:hover { transform: translateY(-6px); box-shadow: 0 8px 25px rgba(0,0,0,0.15); }
.card img { width: 100%; height: 300px; object-fit: contain; margin-bottom: 1rem; }
.card h3 { color: #00c6ff; font-size: 1.3rem; margin-bottom: 0.5rem; }
.card .description { font-size: 0.95rem; color: #555; margin-bottom: 1rem; }
.card .price { font-weight: bold; color: #0072ff; }

/* ----- ENGAGEMENT ----- */
.engagement { background: #0072ff; color: white; padding: 3rem 1rem; text-align: center; border-radius: 20px; margin: 3rem auto; max-width: 800px; }
.engagement h2 { margin-bottom: 1rem; font-size: 2rem; }
.engagement p { font-size: 1.05rem; line-height: 1.6; }

/* ----- FAQ ----- */
.faq { padding: 3rem 1rem; max-width: 800px; margin: 0 auto; }
.faq h2 { font-size: 2rem; margin-bottom: 2rem; color: #0072ff; text-align: center; }
.faq-item { margin-bottom: 1.5rem; }
.faq-item h3 { font-size: 1.2rem; font-weight: bold; color: #00c6ff; }
.faq-item p { font-size: 1rem; color: #555; }

/* ----- CONTACT ----- */
.contact { padding: 3rem 1rem; text-align: center; }
.contact h2 { font-size: 2rem; margin-bottom: 1rem; color: #0072ff; }
.contact form { display: flex; flex-direction: column; gap: 1rem; max-width: 400px; margin: 0 auto; }
.contact input, .contact textarea { padding: 0.8rem; border-radius: 10px; border: 1px solid #ccc; }
.contact button { padding: 0.8rem 1.5rem; border-radius: 30px; border: none; background: #0072ff; color: white; cursor: pointer; font-weight: bold; }
.contact button:hover { background: #005bbb; }
.success { color: #0a8f43; margin-top: 1rem; }

/* ----- GPU ----- */
.gpu {
  padding: 3rem 1rem;
  text-align: center;
  background: #f9f9f9;
}
.gpu h2 { font-size: 2rem; margin-bottom: 1rem; color: #0072ff; }
.gpu p { font-size: 1rem; color: #555; margin-bottom: 2rem; }
.gpu-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 2rem; }
.gpu-card {
  background: white;
  border-radius: 20px;
  padding: 1.5rem;
  box-shadow: 0 4px 15px rgba(0,0,0,0.1);
  transition: 0.3s;
}
.gpu-card:hover { transform: translateY(-6px); box-shadow: 0 8px 25px rgba(0,0,0,0.15); }
.gpu-card img { width: 100%; height: 300px; object-fit: contain; margin-bottom: 1rem; }
.gpu-card h3 { color: #00c6ff; font-size: 1.3rem; margin-bottom: 0.5rem; }
.gpu-desc { font-size: 0.95rem; color: #555; margin-bottom: 0.5rem; }
.gpu-power { font-weight: bold; color: #0072ff; }


/* ----- FOOTER FULL SCREEN ----- */
.footer {
  height: 100vh;
  background: linear-gradient(to bottom, #00c6ff, #0072ff);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 2rem;
}
.footer h2 { font-size: 3rem; margin-bottom: 1rem; }
.footer p { font-size: 1.2rem; margin-bottom: 0.5rem; }
</style>
