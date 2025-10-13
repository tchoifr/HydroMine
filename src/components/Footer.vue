<template>
  <footer class="footer">
    <div class="footer-links left">
      <a href="#about">À propos</a>
      <a href="#solutions">Solutions</a>
      <a href="#durabilite">Durabilité</a>
    </div>

    <div class="footer-center">
      <img src="/public/assets/logo.png" alt="HydroMine Québec" class="footer-logo" />
      <h2>HydroMine Québec</h2>
      <p>Minage durable et rentable, alimenté à 100% par l’hydroélectricité du Québec</p>
      <p class="copyright">© 2025 HydroMine Québec — Tous droits réservés</p>
    </div>

    <div class="footer-links right">
      <a href="#contact">Contact</a>
      <a href="#carriere">Carrières</a>
      <a href="#mentions">Mentions légales</a>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
.footer {
  background-color: #282a2c;
  color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: center;
  padding: 3rem 5%;
  flex-wrap: wrap;
  position: relative;
}

/* ----- CENTRE ----- */
.footer-center {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 500px;
}

.footer-logo {
  width: 220px;
  height: auto;
  margin-bottom: 1rem;
  filter: drop-shadow(0 0 6px #42faff);
}

.footer h2 {
  font-size: 2rem;
  margin-bottom: 0.5rem;
  color: #42faff;
}

.footer p {
  font-size: 1rem;
  margin-bottom: 0.3rem;
  opacity: 0.85;
}

/* ----- LIENS ----- */
.footer-links {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.footer-links a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s, text-shadow 0.3s;
}

.footer-links a:hover {
  color: #42faff;
  text-shadow: 0 0 8px #42faff;
}

/* ----- COPYRIGHT ----- */
.footer .copyright {
  font-size: 0.9rem;
  margin-top: 1rem;
  opacity: 0.6;
}

/* ----- RESPONSIVE ----- */
@media (max-width: 900px) {
  .footer {
    flex-direction: column;
    text-align: center;
  }

  .footer-links {
    flex-direction: row;
    justify-content: center;
    gap: 1.5rem;
    margin-top: 2rem;
  }

  .footer-links.left {
    order: 2;
  }

  .footer-links.right {
    order: 3;
  }

  .footer-center {
    order: 1;
    margin-bottom: 1rem;
  }
}
</style>
