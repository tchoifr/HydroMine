<template>
  <header class="header">
    <video autoplay muted loop class="header-video">
      <source src="/public/assets/header.mp4" type="video/mp4" />
      Votre navigateur ne supporte pas la vidéo.
    </video>

    <div class="nav">
      <div style="width: 130px; height: 85px;" class="logo"><img style="width: 100%; height: 100%; object-fit: cover;" src="/public/assets/logo.png" alt=""></div>
      <nav>
        <a href="#offre">Nos offres</a>
        <a href="#engagement">Engagement</a>
        <a href="#gpu">GPU</a>
        <a href="#contact">Contact</a>
      </nav>
      <button class="btn-login">Connexion</button>
    </div>

    <div class="header-content">
      <h1 style="color: #42faff;">HydroMine Québec</h1>
      <p>Le minage éco-responsable, propulsé par la puissance de l’eau.
Performant. Durable. 100 % énergie verte.</p>
      <a href="#offre" class="cta-btn">Découvrir nos cartes</a>
    </div>
  </header>
</template>

<script setup>
</script>
