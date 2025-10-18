<template>
  <footer class="footer">
    <!-- Left links -->
    <div class="footer-links left">
      <a href="#offre">Our Offers</a>
      <a href="#engagement">Commitment</a>
      <a href="#gpu">Ecosystem</a>
    </div>

    <!-- Center -->
    <div class="footer-center">
      <img src="/public/assets/logoPanda.png" alt="Panda Paulownia" class="footer-logo" />
      <h2>Panda Paulownia</h2>
      <p>
        Invest in nature and innovation 🌿<br />
        Sustainable mining powered by blockchain and crypto.
      </p>
      <p class="copyright">© 2025 Panda Paulownia — All rights reserved</p>
    </div>

    <!-- Right links -->
    <div class="footer-links right">
      <a href="#contact">Contact</a>
      <a href="#mentions">Legal Notice</a>
    </div>
  </footer>
</template>


<script setup>
</script>

<style scoped>
.footer {
  background-color: #1a1a1d;
  color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: center;
  padding: 3rem 5%;
  flex-wrap: wrap;
  position: relative;
  border-top: 2px solid #b173ff;
}

/* ----- CENTRE ----- */
.footer-center {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 500px;
}

.footer-logo {
  width: 160px;
  height: auto;
  margin-bottom: 1rem;
  filter: drop-shadow(0 0 6px #b173ff);
}

.footer h2 {
  font-size: 2rem;
  margin-bottom: 0.5rem;
  color: #b173ff;
  font-weight: 700;
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
  color: #b173ff;
  text-shadow: 0 0 8px #b173ff;
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
    flex-direction: column;
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
    max-width: 265px;
  }

}
</style>
