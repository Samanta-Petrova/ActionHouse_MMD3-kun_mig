<script setup>
import Header from '../components/navigation.vue'
import Footer from '../components/Footer.vue'
import Galleri from '../components/Galleri.vue'
</script>

<template>
  <Header />

  <!-- Hero image udenfor container -->
  <img
    src="../../assets/img/bowlingHeroIMG.webp"
    alt="Bowling baner hos Action House"
    class="hero-image"
  />

  <main class="bowling-page">
    <section class="intro">
      <h1>Moderne bowlingbaner</h1>

      <p>
        Vores nye bowlingbaner er udstyret med bløde loungesofaer og praktiske cafeborde,
        perfekt til at slappe af med en sodavand, drink eller en af vores 12 forskellige øl på fad,
        mens I hepper på hinanden.
      </p>

      <p>Vi har gjort det nemt for både børn og voksne at spille sammen:</p>

      <ul>
        <li>Fuldautomatiske børnebander, der kører op for børnene og ned for voksne</li>
        <li>Navneindtastning håndteres af vores personale, så I hurtigt kan komme i gang</li>
      </ul>
    </section>

    <section class="info-grid">
      <article class="info-card">
        <h3>Bowling info</h3>
        <ul>
          <li>Antal baner, 8</li>
          <li>Børnebaner på alle baner</li>
          <li>Max 6 personer pr. bane</li>
        </ul>
      </article>

      <article class="info-card">
        <h3>Bowling priser</h3>
        <ul>
          <li>Bane pr. time 239,-</li>
          <li>Powerbowling 279,- pr. bane pr. time</li>
          <li>Skoleje 15,-</li>
          <li>Spis og bowl fra 219,-</li>
          <li>Buffet og bowl fra 239,-</li>
          <li>Børnebuffet og bowl fra 149,-</li>
        </ul>
      </article>

      <article class="info-card">
        <h3>Power bowlingpakker</h3>
        <ul>
          <li>Spirituspakken til 699,- kr.</li>
          <li>Ølpakken til 478,- kr.</li>
          <li>Drinkspakken til 449,- kr.</li>
          <li>Shotspakken til 679,- kr.</li>
        </ul>

        <a href="/powerbowling" class="read-more">
          Læs mere om pakker →
        </a>
      </article>
    </section>

    <section class="power-bowling">
      <h2>Power Bowling, fest og action</h2>

      <p>
        Hver aften fra kl. 21.00 forvandler vi bowlingbanerne til Power Bowling
        med lys, musik og masser af sjov.
      </p>

      <p>Sådan fungerer det:</p>

      <ul>
        <li>Slår du en strike, når den røde kegle står forrest, får hele banen et shot</li>
        <li>Husk at informere vores personale ved baren inden du kaster, ellers tæller det ikke</li>
      </ul>

      <p>
        Power Bowling tider, dagligt fra 21.00 til 22 eller 24.00
      </p>

      <p>
        Book din bane nu, +45 9967 6710, og gør klar til en aften med sjov,
        bowling og festlig stemning.
      </p>

      <a href="/booking" class="bowlingButton">Book nu</a>
    </section>

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
  margin: 0;
  display: block;
}

.bowling-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  padding-top: 0;
}

.intro h1 {
  color: #154B82;
  margin-bottom: 1rem;
}

.intro p,
.intro ul {
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
  height: 100%;
}

.info-card h3 {
  color: #154B82;
  margin-bottom: 1rem;
}

.info-card li {
  margin-left: 0rem;
}

.read-more {
  display: inline-block;
  margin-top: 1rem;
  color: #154B82;
  text-decoration: underline;
}

.power-bowling {
  margin-top: 4rem;
}

.power-bowling h2 {
  color: #154B82;
  margin-bottom: 1rem;
}

.cta-button {
  display: inline-block;
  margin-top: 2rem;
  padding: 0.8rem 2rem;
  background: #D41E2A;
  color: white;
  border-radius: 8px;
  text-decoration: none;
}

.galleriSpacer {
  margin-top: 5rem;
}

.bowlingButton {
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

.bowlingButton:hover {
  background-color: #154B82;
}
</style>
