<script setup>
import Header from '../components/navigation.vue'
import Footer from '../components/Footer.vue'
import Galleri from '../components/Galleri.vue'
import breadcrumbs from '../components/breadcrumbs.vue'
</script>

<template>
  <Header />

  <img
    src="../../assets/img/Lasergame.webp"
    alt="Lasergame hos Action House"
    class="lasergame-hero"
  />

  <breadcrumbs />

  <main class="lasergame-page">
    <section class="lasergame-intro">
      <h1>Lasergame</h1>

      <p>
        Dit hjerte hamrer, sveden siver og du i dit es, når du dyster mod fjenden.
        Det nye Laser Maxx lasergame udstyr er det førende på det europæiske marked.
        De mange funktioner i Laser Maxx udstyret sørger for, at du får en underholdende
        oplevelse med din familie, venner eller kollegaer. En tur i Lasergame i Action House
        Løkken giver dig en oplevelse du aldrig glemmer. Vi gør opmærksomme på, at på nogle
        dage pga. travlhed vil man kunne komme til og spille med sammen med andre grupper/familier.
      </p>

      <h3>Om lasergame spillet</h3>
      <p>
        Banen er 600 kvm i 3 etager. Det er bane nok til, at maksimalt 35 personer og minimum 2 personer,
        kan lade jagten gå ind! Man kan spille alle mod alle, eller i hold op til 6 forskellige farver.
        Spiller man i hold, har hvert hold en powerboks man skal beskytte og selvfølgelig skyde modstanderens.
      </p>

      <h3>Vesten tæller alle pointene sammen:</h3>
      <ul>
        <li>100 point for at ramme en modstander.</li>
        <li>-25 for at ramme en medspiller.</li>
        <li>-50 point hver gang man bliver ramt.</li>
      </ul>
    </section>

    <section class="lasergame-info-grid">
      <article class="lasergame-card">
        <h3>Pris per pers.</h3>
        <ul>
          <li>12 min. 75,- kr.</li>
          <li>20 min. 95,- kr.</li>
          <li>30 min 120,- kr.</li>
        </ul>
      </article>

      <article class="lasergame-card">
        <h3>Tilbudspakker</h3>
        <p>Action Pakken: fra 235,- kr per pers</p>
        <ul>
          <li>10 min gokart</li>
          <li>12 min lasergame</li>
          <li>55 min bowling</li>
        </ul>
        <p>Dameaften: fra 209,- kr per pers</p>
        <ul>
          <li>Skydesimulator</li>
          <li>20 min lasergame</li>
          <li>55 min bowling</li>
        </ul>
        <a href="/tilbudspakker" class="lasergame-read-more">Læs mere om pakker →</a>
      </article>

      <article class="lasergame-card">
        <h3>Lasergame Info</h3>
        <ul>
          <li>Banen er i 3 etager</li>
          <li>600 m2</li>
          <li>Op til 32 spillere af gangen</li>
          <li>Laser Maxx veste og pistoler</li>
          <li>Op til 6 forskellige holdfarver</li>
          <li>Pointkort til alle deltagere</li>
        </ul>
      </article>
    </section>

    <section class="lasergame-rules">
      <h2>Spille regler</h2>
      <p>
        Når man er ramt og død, går lyset i vesten ud og pistolen virker ikke i 5 sekunder,
        og vesten vil sige ”don't give up, dont give up, og tilsidst keep going”.
        (vesten siger ”well done” når man rammer en modstander) Man er så død i 5 sekunder
        men kan først blive skudt igen, efter 6 sekunder, så man har et sekunds forspring
        over for de andre når man har været død. Derudover kan man på displayet på vesten
        se hvem det er der har ramt en. Når spillet er slut vil resultatet fremkomme ved
        tjek ind i lasergame på tv-skærmen. Man kan også få en udskrift med af spillet,
        hvorpå man kan se, hvor mange gange man har skudt hinanden hver i sær, hvor mange
        skud man har brugt og, hvor god en procentramme man har.
      </p>

      <h2>Flere spilmuligheder</h2>
      <p>
        Vi udviklet lidt på vores lasergame spil, så hvis man har en træfsikkerhed på over
        20 procent får man 500 point i bonus. Vi har også fået sat en ny spilmulighed op,
        som hedder multiboks og reflektor, det betyder at, der sidder nogle bokse på væggen
        inde på banen (3 stk.), hvor man kan gå over, og skyde på en af dem 3 gange med 5
        minimum sek. mellemrum (dog skal det være inden for 2 min.) så kan man få 75 point
        og en random superpower.<br><br>
        Den superpower man kan få er maskinpistol, sniper, usynlighed (lyset på vesten går
        ud ligesom når man er død) lydløshed eller man kan få et skjold, så man ikke kan dø
        og blive ramt. Disse powers virker kun for 1 minut, men så kan man skyde på boksene
        igen. Man skal dog være opmærksom på at boksene kan skyde igen og hvis de rammer en
        mister man 75 point.
      </p>

      <a href="/booking" class="lasergame-button">Book nu</a>
    </section>

    <Galleri class="lasergame-gallery" />
  </main>

  <Footer />
</template>

<style scoped>
.lasergame-hero {
  width: 100vw;
  height: 50vh;
  object-fit: cover;
  object-position: center 30%;
  display: block;
}

.lasergame-page {
  max-width: 100%;
  margin: 0 auto;
  margin-left: 8.65625rem;
  margin-right: 8.65625rem;
  padding-top: 0;
}

.lasergame-intro h1,
.lasergame-intro h3,
.lasergame-card h3,
.lasergame-rules h2 {
  color: #154B82;
  margin-bottom: 1rem;
}

.lasergame-info-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  margin: 3rem 0;
}

.lasergame-card {
  background: rgba(21, 75, 130, 0.25);
  padding: 1.5rem;
  border-radius: 12px;
}

.lasergame-card h3 {
  font-size: 2rem;
  margin-top: 0;
}

.lasergame-read-more {
  display: inline-block;
  margin-top: 1rem;
  color: #154B82;
  text-decoration: underline;
}

.lasergame-gallery {
  margin-top: 5rem;
}

.lasergame-button {
  display: block;
  width: 4rem;
  margin: 2rem auto 0 auto;
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

.lasergame-button:hover {
  background-color: #154B82;
}

@media (max-width: 600px) {
  .lasergame-page {
    margin-left: 1rem;
    margin-right: 1rem;
  }
  .lasergame-info-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  .lasergame-card {
    padding: 1rem;
  }
  .lasergame-card h3 {
    font-size: 1.2rem;
  }
  .lasergame-card p,
  .lasergame-card ul li {
    font-size: 0.95rem;
  }
  .lasergame-intro h1 {
    font-size: 1.5rem;
    text-align: center;
  }
  .lasergame-intro p {
    font-size: 0.95rem;
  }
  .lasergame-intro h3 {
    font-size: 1.2rem;
  }
  .lasergame-rules h2 {
    font-size: 1.3rem;
  }
  .lasergame-rules p {
    font-size: 0.95rem;
  }
  .lasergame-button {
    width: auto;
    padding: 0.75rem 1.5rem;
    font-size: 0.95rem;
  }
  *{
    line-height: 1.5rem;
  }
}
</style>
