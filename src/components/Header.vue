<template>
  <header class="header">
    <video autoplay muted loop class="header-video">
      <source src="/assets/header.mp4" type="video/mp4" />
      Votre navigateur ne supporte pas la vidéo.
    </video>

    <div class="nav">
      <div class="logo">
        <img src="/assets/logoPanda.png" alt="Panda Paulownia" />
      </div>

      <!-- Liens desktop -->
      <nav class="nav-links">
        <a href="#offre">Nos offres</a>
        <a href="#engagement">Engagement</a>
        <a href="#gpu">Ecosystème</a>
        <a href="#contact">Contact</a>
      </nav>

      <!-- Bouton hamburger mobile -->
      <button
        class="hamburger"
        :class="{ open: isOpen }"
        @click="toggleMenu"
        aria-label="Menu"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>

    <!-- Menu mobile -->
    <transition name="fade">
      <div v-if="isOpen" class="mobile-menu" @click.self="closeMenu">
        <a href="#offre" @click="closeMenu">Nos offres</a>
        <a href="#engagement" @click="closeMenu">Engagement</a>
        <a href="#gpu" @click="closeMenu">Ecosystème</a>
        <a href="#contact" @click="closeMenu">Contact</a>
      </div>
    </transition>

    <!-- Contenu principal -->
    <div class="header-content">
      <h1 style="color: #b173ff;">Panda paulownia</h1>
      <p>
        Investis en nature et en innovation : paye en crypto pour faire pousser ton
        <strong>paulownia</strong>, un arbre unique qui te génère une
        <strong>rente à chaque vente</strong>.<br />
        Durable. Rentable. Alimenté par la blockchain.
      </p>
      <a href="https://coinmarketcap.com/" class="cta-btn" style="font-size: xx-large;">
        Accédez à notre crypto PPA 💎
      </a>
    </div>
  </header>
</template>

<script setup>
import { ref, watch, onMounted, onBeforeUnmount } from "vue";

const isOpen = ref(false);

const toggleMenu = () => (isOpen.value = !isOpen.value);
const closeMenu = () => (isOpen.value = false);

// Bloque le scroll du body quand le menu est ouvert
watch(isOpen, (open) => {
  document.documentElement.style.overflow = open ? "hidden" : "";
});

// Ferme le menu si on repasse sur desktop
const onResize = () => {
  if (window.innerWidth >= 1024 && isOpen.value) closeMenu();
};

onMounted(() => window.addEventListener("resize", onResize));
onBeforeUnmount(() => window.removeEventListener("resize", onResize));
</script>

<style scoped>
/* ===== HEADER GLOBAL ===== */
.header {
  position: relative;
  overflow: hidden;
  min-height: 75vh;
  color: #fff;
  text-align: center;
}

.header-video {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: brightness(0.6);
  z-index: 0;
}

/* ===== NAVBAR ===== */
.nav {
  position: relative;
  z-index: 2;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
}

.logo {
  width: 130px;
  height: 85px;
}
.logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

/* Liens desktop */
.nav-links {
  display: none;
  gap: 1.5rem;
}
.nav-links a {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  position: relative;
}
.nav-links a::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: #b173ff;
  transition: width 0.25s ease;
}
.nav-links a:hover::after {
  width: 100%;
}

/* ===== HAMBURGER ===== */
.hamburger {
  width: 42px;
  height: 42px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 6px;
  background: rgba(0, 0, 0, 0.35);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  cursor: pointer;
  z-index: 10;
  transition: transform 0.2s ease;
}
.hamburger:active {
  transform: scale(0.95);
}
.hamburger span {
  width: 22px;
  height: 2px;
  background: white;
  border-radius: 2px;
  transition: all 0.25s ease;
}

/* Animation croix */
.hamburger.open span:nth-child(1) {
  transform: translateY(8px) rotate(45deg);
}
.hamburger.open span:nth-child(2) {
  opacity: 0;
}
.hamburger.open span:nth-child(3) {
  transform: translateY(-8px) rotate(-45deg);
}

/* ===== MENU MOBILE ===== */
.mobile-menu {
  position: fixed;
  inset: 0;
  background: rgba(15, 12, 24, 0.95);
  backdrop-filter: blur(4px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 24px;
  z-index: 5;
      top: 105px;

  animation: fadeIn 0.25s ease;
}
.mobile-menu a {
  color: #fff;
  font-size: 1.3rem;
  text-decoration: none;
  transition: color 0.2s;
}
.mobile-menu a:hover {
  color: #b173ff;
}
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* Transition fondu */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* ===== CONTENU HEADER ===== */
.header-content {
  position: relative;
  z-index: 1;
  padding: 40px 16px 80px;
}
.cta-btn {
  display: inline-block;
  background: #b173ff;
  color: white;
  text-decoration: none;
  padding: 12px 24px;
  border-radius: 8px;
  font-weight: bold;
  transition: background 0.25s ease;
}
.cta-btn:hover {
  background: #9d5aff;
}

/* ===== RESPONSIVE ===== */
@media (min-width: 1024px) {
  .nav-links {
    display: flex;
  }
  .hamburger {
    display: none;
  }
  .mobile-menu {
    display: none;
  }
  .header-content {
    padding-top: 60px;
  }
}
</style>
