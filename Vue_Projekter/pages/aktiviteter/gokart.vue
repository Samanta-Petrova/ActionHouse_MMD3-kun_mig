<script setup>
import Header from '../components/navigation.vue'
import Footer from '../components/Footer.vue'
import Galleri from '../components/Galleri.vue'
import breadcrumbs from '../components/breadcrumbs.vue'
</script>

<template>
  <Header />

  <img
    src="../../assets/img/GokartKoersel.webp"
    alt="Gokart baner hos Action House"
    class="gokart-hero"
  />

  <breadcrumbs />

  <main class="gokart-page">
    <section class="gokart-intro">
      <h1>Gokart i Nordjylland - Kør stærkt på en af danmarks største indendørs gokartbaner.</h1>

      <p>
        Oplev gokart i verdensklasse hos Action House i Løkken. Er du klar til at mærke suset fra ægte gokart-action? Hos Action House i Løkken finder du en af Danmarks største og hurtigste indendørs gokartbaner – spækket med fart, spænding og adrenalinkick.
      </p>

      <p>
        Vores gokartbane er 1,1 km lang og er gennem årene blevet udvidet og forbedret flere gange, så du i dag kan prøve kræfter med en af Nordeuropas mest imponerende gokartbaner. Uanset om du er nybegynder eller rutineret racerkører, venter der dig en uforglemmelig oplevelse med høj fart og skarpe sving.
      </p>
    </section>

    <section class="gokart-info-grid">
      <article class="gokart-card">
        <h3>Priser</h3>
        <p>Alm. Kørsel</p>
        <ul>
          <li>Gokart 10 min: 145,-</li>
          <li>Gokart 15 min: 195,-</li>
        </ul>
      </article>

      <article class="gokart-card">
        <h3>Tilbudspakker</h3>
        <p>Formel 1. 25 min: 295,- kr</p>
        <ul>
          <li>15 min. Tidskørsel</li>
          <li>10 min. Finale</li>
        </ul>
        <p>Formel 1. 50 min: 578,- kr.</p>
        <ul>
          <li>10 min Opvarmning</li>
          <li>15 min Tidskørsel</li>
          <li>25 min Finale</li>
        </ul>
        <a href="/tilbudspakker" class="gokart-read-more">Læs mere om pakker →</a>
      </article>

      <article class="gokart-card">
        <h3>Krav</h3>
        <ul>
          <li>Min. højde 120 cm</li>
          <li>Min. 7 år</li>
          <li>Ædruelighed 0,0</li>
          <li>Hjelmhue (20,-)</li>
          <li>Fuld førlighed i arme og ben</li>
          <li>Ingen tørklæder og løshængende tøj</li>
        </ul>
      </article>
    </section>

    <section class="gokart-info">
      <h2>Praktisk info om vores gokartbane</h2>

      <ul class="gokart-list">
        <li>Beliggenheden: Kun ca. 20 km fra Hjørring og Brønderslev og 45 km fra Aalborg</li>
        <li>Kapacitet: Op til 20 gokarts på banen samtidig.</li>
        <li>Aldersgrænse: Man skal være fyldt 7 år og være 120 cm høj.</li>
        <li>Gokarts: Vi har 3 størrelser gokarts og det er udelukkende personalet der bestemmer hvilken man får tildelt.</li>
        <li>Bemærk: Ved grupper på under 20 personer kan der forekomme samkørsel med andre.</li>
        <li>Sikkerhed: Alkohol før kørsel er ikke tilladt – personalet vurderer køreegnethed.</li>
        <li>Krav: Fuld førlighed i begge arme og ben, samt lukkede sko, ingen tørklæder eller løst hængende tøj.</li>
        <li>Instruktion: Alle får altid instruktion inden kørsel uanset hvor mange gange man har kørt.</li>
        <li>Obligatorisk: Hvis ikke man har egen hjelm med skal man have balaclava/hjelmhue – disse kan købes hos os.</li>
        <li>Ekstra udstyr: Kørehandsker kan tilkøbes for kun 35,- (str. S, M, L, XL)</li>
      </ul>

      <a href="/booking" class="gokart-button">Book nu</a>
    </section>

    <Galleri class="gokart-gallery" />
  </main>

  <Footer />
</template>

<style scoped>
.gokart-hero {
  width: 100vw;
  height: 50vh;
  object-fit: cover;
  object-position: center 60%;
  margin: 0;
  display: block;
}

.gokart-page {
  max-width: 100%;
  margin-left: 8.65625rem;
  margin-right: 8.65625rem;
  padding-top: 0;
}

.gokart-intro h1 {
  color: #154B82;
  margin-bottom: 1rem;
}

.gokart-intro p {
  margin-bottom: 1rem;
}

.gokart-info-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  margin: 3rem 0;
}

.gokart-card {
  background: rgba(21, 75, 130, 0.25);
  padding: 1.5rem;
  border-radius: 12px;
}

.gokart-card h3 {
  color: #154B82;
  margin-bottom: 1rem;
}

.gokart-card p {
  font-size: 1.2rem;
}

.gokart-read-more {
  display: inline-block;
  margin-top: 1rem;
  color: #154B82;
  text-decoration: underline;
}

.gokart-info {
  margin-top: 4rem;
}

.gokart-info h2 {
  color: #154B82;
  margin-bottom: 1rem;
}

.gokart-gallery {
  margin-top: 5rem;
}

.gokart-button {
  display: block;
  width: 4rem;
  margin: 2rem auto 0 auto;
  padding: 0.75rem 2.5rem;
  background-color: #D41E2A;
  color: #ffffff;
  border: none;
  border-radius: var(--desktopBorder);
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.5s ease;
  text-align: center;
}

.gokart-button:hover {
  background-color: #154B82;
}

.gokart-list li {
  margin-bottom: 1rem;
}

@media (max-width: 600px) {
  .gokart-page {
    margin-left: 1rem;
    margin-right: 1rem;
  }
  .gokart-info-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  .gokart-card {
    padding: 1rem;
  }
  .gokart-card h3 {
    font-size: 1.2rem;
  }
  .gokart-card p,
  .gokart-card ul li {
    font-size: 0.95rem;
  }
  .gokart-intro h1 {
    font-size: 1.5rem;
    text-align: center;
  }
  .gokart-intro p {
    font-size: 0.95rem;
  }
  .gokart-info h2 {
    font-size: 1.3rem;
    text-align: center;
  }
  .gokart-info p,
  .gokart-info ul li {
    font-size: 0.95rem;
  }
  .gokart-button {
    width: auto;
    padding: 0.75rem 1.5rem;
    font-size: 0.95rem;
  }
}
</style>
