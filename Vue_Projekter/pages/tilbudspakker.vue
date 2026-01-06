<script setup>
import { ref } from 'vue'
import Header from '../components/navigation.vue'
import Footer from '../components/Footer.vue'

const activeCategory = ref('all')
</script>

<template>
  <Header />

  <img
    src="../assets//img/tilbudsHero.webp"
    alt="Tilbudspakker hos Action House"
    class="gokart-hero"
  />

  <main class="gokart-page">
    <section class="gokart-intro">
      <h1>Tilbudspakker</h1>
      <p>
        Med vores tilbudspakker har vi gjort det nemt at få en komplet oplevelse hos Action House Funcenter.
        Pakkerne er sammensat med fokus på sjov, variation og fællesskab, så I kan kombinere flere aktiviteter
        i én samlet løsning.
      </p>
    </section>

    <nav class="package-nav">
      <button @click="activeCategory = 'all'" :class="{ active: activeCategory === 'all' }">Tilbudspakker</button>
      <button @click="activeCategory = 'action'" :class="{ active: activeCategory === 'action' }">Action pakker</button>
      <button @click="activeCategory = 'dameherre'" :class="{ active: activeCategory === 'dameherre' }">Dame- og herre pakker</button>
      <button @click="activeCategory = 'gokart'" :class="{ active: activeCategory === 'gokart' }">Gokart</button>
    </nav>

    <section v-if="activeCategory === 'all'">
      <h3 class="category-title">Action pakker</h3>
      <div class="gokart-info-grid">
        <article class="gokart-card">
          <h3>Action pakke</h3>
          <ul>
            <li>10 min gokart</li>
            <li>12 min lasergame</li>
            <li>55 min bowling</li>
          </ul>
          <p>Pris: 239,- kr. / inkl. spisning: 399,- / buffet: 419,-</p>
        </article>

        <article class="gokart-card">
          <h3>Lux Action</h3>
          <ul>
            <li>25 min gokart</li>
            <li>20 min lasergame</li>
            <li>55 min bowling</li>
          </ul>
          <p>Pris: 399,- kr. / inkl. spisning: 559,- / buffet: 579,-</p>
        </article>

        <article class="gokart-card">
          <h3>Mega Action</h3>
          <ul>
            <li>25 min gokart</li>
            <li>20 min lasergame</li>
            <li>55 min bowling</li>
          </ul>
          <p>Pris pr. pers.      399,- kr. inkl. spisning     559,- kr. inkl. buffet          579,- kr.</p>
        </article>

        <article class="gokart-card">
          <h3>VR Action Pakke</h3>
          <ul>
            <li>12 min VR</li>
            <li>10 min gokart</li>
            <li>12 min lasergame</li>
          </ul>
          <p>Pris: 309,- kr. / inkl. spisning: 469,- / buffet: 489,-</p>
        </article>

        <article class="gokart-card">
          <h3>Lux VR Action Pakke</h3>
          <ul>
            <li>24 min Virtuel Reality</li>
            <li>25 min gokart formel 1</li>
            <li>20 min lasergame</li>
          </ul>
          <p>Pris pr. pers.       525,-  kr. inkl. spisning      685,- kr. inkl. buffet          705,- kr.</p>
        </article>
      </div>

      <h3 class="category-title">Dame- og herre pakker</h3>
      <div class="gokart-info-grid">
        <article class="gokart-card">
          <h3>Dameaften</h3>
          <ul>
            <li>Skydesimulator</li>
            <li>20 min lasergame</li>
            <li>55 min bowling</li>
          </ul>
          <p>Pris: 209,- kr. / inkl. spisning: 369,- / buffet: 389,-</p>
        </article>

        <article class="gokart-card">
          <h3>Herreaften</h3>
          <ul>
            <li>25 min gokart</li>
            <li>Skydesimulator</li>
            <li>55 min bowling</li>
          </ul>
          <p>Pris: 399,- kr. / inkl. spisning: 559,- / buffet: 579,-</p>
        </article>
      </div>

      <h3 class="category-title">Gokart</h3>
      <div class="gokart-info-grid">
        <article class="gokart-card">
          <h3>Formel 1</h3>
          <ul>
            <li>15 min tidstagning</li>
            <li>10 min finale</li>
          </ul>
          <p>Pris: 295,- kr. / inkl. spisning: 455,- / buffet: 475,-</p>
        </article>

        <article class="gokart-card">
          <h3>Lux Formel 1</h3>
          <ul>
            <li>25 min tidstagning</li>
            <li>25 min finale</li>
          </ul>
          <p>Pris: 578,- kr. / inkl. spisning: 738,- / buffet: 758,-</p>
        </article>

        <article class="gokart-card">
          <h3>Le Mans</h3>
          <ul>
            <li>50 min holdkørsel</li>
            <li>Min. 18 hold (2-4 pers.)</li>
            <li>Min. 36 pers.</li>
          </ul>
          <p>Pris: 749,- kr. pr. kart / mad: +160,- / buffet: +180,-</p>
        </article>
      </div>
    </section>

    <section v-if="activeCategory === 'action'" class="gokart-info-grid">
      <article class="gokart-card">
        <h3>Action pakke</h3>
        <ul>
          <li>10 min gokart</li>
          <li>12 min lasergame</li>
          <li>55 min bowling</li>
        </ul>
        <p>Pris: 239,- kr. / inkl. spisning: 399,- / buffet: 419,-</p>
      </article>

      <article class="gokart-card">
        <h3>Lux Action</h3>
        <ul>
          <li>25 min gokart</li>
          <li>20 min lasergame</li>
          <li>55 min bowling</li>
        </ul>
        <p>Pris: 399,- kr. / inkl. spisning: 559,- / buffet: 579,-</p>
      </article>

      <article class="gokart-card">
        <h3>Mega Action</h3>
        <ul>
          <li>25 min gokart</li>
          <li>20 min lasergame</li>
          <li>55 min bowling</li>
        </ul>
        <p>Pris pr. pers.      399,- kr. inkl. spisning     559,- kr. inkl. buffet          579,- kr.</p>
      </article>

      <article class="gokart-card">
        <h3>VR Action Pakke</h3>
        <ul>
          <li>12 min VR</li>
          <li>10 min gokart</li>
          <li>12 min lasergame</li>
        </ul>
        <p>Pris: 309,- kr. / inkl. spisning: 469,- / buffet: 489,-</p>
      </article>

      <article class="gokart-card">
        <h3>Lux VR Action Pakke</h3>
        <ul>
          <li>24 min Virtuel Reality</li>
          <li>25 min gokart formel 1</li>
          <li>20 min lasergame</li>
        </ul>
        <p>Pris pr. pers.       525,-  kr. inkl. spisning      685,- kr. inkl. buffet          705,- kr.</p>
      </article>
    </section>

    <section v-if="activeCategory === 'dameherre'" class="gokart-info-grid">
      <article class="gokart-card">
        <h3>Dameaften</h3>
        <ul>
          <li>Skydesimulator</li>
          <li>20 min lasergame</li>
          <li>55 min bowling</li>
        </ul>
        <p>Pris: 209,- kr. / inkl. spisning: 369,- / buffet: 389,-</p>
      </article>

      <article class="gokart-card">
        <h3>Herreaften</h3>
        <ul>
          <li>25 min gokart</li>
          <li>Skydesimulator</li>
          <li>55 min bowling</li>
        </ul>
        <p>Pris: 399,- kr. / inkl. spisning: 559,- / buffet: 579,-</p>
      </article>
    </section>

    <section v-if="activeCategory === 'gokart'" class="gokart-info-grid">
      <article class="gokart-card">
        <h3>Formel 1</h3>
        <ul>
          <li>15 min tidstagning</li>
          <li>10 min finale</li>
        </ul>
        <p>Pris: 295,- kr. / inkl. spisning: 455,- / buffet: 475,-</p>
      </article>

      <article class="gokart-card">
        <h3>Lux Formel 1</h3>
        <ul>
          <li>25 min tidstagning</li>
          <li>25 min finale</li>
        </ul>
        <p>Pris: 578,- kr. / inkl. spisning: 738,- / buffet: 758,-</p>
      </article>

      <article class="gokart-card">
        <h3>Le Mans</h3>
        <ul>
          <li>50 min holdkørsel</li>
          <li>Min. 18 hold (2-4 pers.)</li>
          <li>Min. 36 pers.</li>
        </ul>
        <p>Pris: 749,- kr. pr. kart / mad: +160,- / buffet: +180,-</p>
      </article>
    </section>

    <a href="/booking" class="gokart-button">Book nu</a>
  </main>

  <Footer />
</template>

<style scoped>
.gokart-hero {
  width: 100vw;
  height: 50vh;
  object-fit: cover;
  object-position: center 50%;
  margin: 0;
  display: block;
}

.gokart-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  padding-top: 0;
}

.gokart-intro h1 {
  color: #154B82;
  margin-bottom: 1rem;
}

.category-title,
.gokart-card h3 {
  color: #154B82;
  margin-bottom: 1rem;
}

.package-nav {
  display: flex;
  gap: 1rem;
  margin: 2rem 0;
  justify-content: center;
  flex-wrap: wrap;
}

.package-nav button {
  background-color: #F6B2B7;
  color: white;
  border: none;
  padding: 0.6rem 1.5rem;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

.package-nav button:hover,
.package-nav button.active {
  background-color: #D41E2A;
}

.gokart-info-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.gokart-card {
  background: rgba(21, 75, 130, 0.25);
  padding: 1.5rem;
  border-radius: 12px;
}

.gokart-card p {
  font-size: 1.1rem;
  margin-top: 1rem;
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

</style>
