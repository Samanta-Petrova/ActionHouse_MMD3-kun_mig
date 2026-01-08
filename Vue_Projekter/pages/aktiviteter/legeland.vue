<script setup>
import Header from '../components/navigation.vue'
import Footer from '../components/Footer.vue'
import Galleri from '../components/Galleri.vue'
import breadcrumbs from '../components/breadcrumbs.vue'
</script>

<template>
  <Header />

  <img
    src="../../assets/img/Legeland.webp"
    alt="Legeland hos Action House"
    class="hero-image"
  />

  <breadcrumbs />

  <main class="bowling-page">
    <section class="intro">
      <h1>Sjov og action til hele familien</h1>
      <p>
        Oplev vores nye legeland. Det perfekte sted for hele familien!<br>
        Uanset om du har små tumlinger eller aktive tweens med, er der noget for alle aldersgrupper
        i vores farverige og sikre univers. Med den nye udvidelse byder vi velkommen til endnu flere
        muligheder for sjov og kreativ leg til både små og store legebørn.
      </p>
    </section>

    <section class="info-grid">
      <article class="info-card">
        <h3>Dagsbillet</h3>
        <h4>Mandag - Torsdag</h4>
        <ul>
          <li>Barn under 1 år - 0,-</li>
          <li>Barn 1-3 år - 69,-</li>
          <li>Barn 4-17 år - 79,-</li>
          <li>Voksne - 49,-</li>
        </ul>

        <h4>Weekender, Skoleferier og Helligdage</h4>
        <ul>
          <li>Barn under 1 år - 0,-</li>
          <li>Barn 1-3 år - 79,-</li>
          <li>Barn 4-17 år - 119,-</li>
          <li>Voksne - 49,-</li>
        </ul>
      </article>

      <article class="info-card">
        <h3>Børnefødselsdag</h3>
        <p>
          Hverdage (mandag-torsdag) 120,- pr. barn<br>
          Weekender og helligdage, samt skoleferier 140,- pr. barn
        </p>
        <a href="/tilbudspakker" class="read-more">Læs mere om pakken →</a>
      </article>

      <article class="info-card">
        <h3>Aktiviteter</h3>
        <ul>
          <li>Forhindringsbaner</li>
          <li>Rutsjebaner</li>
          <li>Trampoliner</li>
          <li>Tumleområder</li>
          <li>Interaktive spilzoner</li>
          <li>Boldspil</li>
        </ul>
      </article>
    </section>

    <a href="/booking" class="bowlingButton">Book nu</a>

    <Galleri class="galleriSpacer" />
  </main>

  <Footer />
</template>

<style scoped>
.hero-image {
  width: 100vw;
  height: 50vh;
  object-fit: cover;
  object-position: center 30%;
  display: block;
}

.bowling-page {
  max-width: 100%;
  margin: 0 auto;
  margin-left: 8.65625rem;
  margin-right: 8.65625rem;
  padding-top: 0;
}

.intro h1,
.info-card h3 {
  color: #154B82;
  margin-bottom: 1rem;
}

.intro p {
  margin-bottom: 1rem;
}

.info-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  margin: 3rem 0;
}

.info-card {
  background: rgba(21, 75, 130, 0.25);
  padding: 1.5rem;
  border-radius: 12px;
}

.info-card h3 {
  font-size: 2rem;
  margin-top: 0;
}

.info-card h4 {
  color: #000;
  font-size: 1.2rem;
  margin: 1rem 0 0.5rem 0;
}

.read-more {
  display: inline-block;
  margin-top: 1rem;
  color: #154B82;
  text-decoration: underline;
}

.galleriSpacer {
  margin-top: 5rem;
}

.bowlingButton {
  display: block;
  width: 4rem;
  margin: 4rem auto 0 auto; 
  padding: 0.75rem 2.5rem;
  background-color: #D41E2A;
  color: #fff;
  border: none;
  border-radius: var(--desktopBorder);
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.5s ease;
  text-align: center;
}

.bowlingButton:hover {
  background-color: #154B82;
}

@media (max-width: 600px) {
  .bowling-page {
    margin-left: 1rem;
    margin-right: 1rem;
  }
  .info-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  .info-card {
    padding: 1rem;
  }
  .info-card h3 {
    font-size: 1.2rem;
  }
  .info-card h4 {
    font-size: 1rem;
  }
  .info-card p,
  .info-card ul li {
    font-size: 0.95rem;
  }
  .intro h1 {
    font-size: 1.5rem;
    text-align: center;
  }
  .intro p {
    font-size: 0.95rem;
  }
  .bowlingButton {
    width: auto;
    padding: 0.75rem 1.5rem;
    font-size: 0.95rem;
  }
}
</style>
