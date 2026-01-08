<script setup>
import Header from '../components/navigation.vue'
import Footer from '../components/Footer.vue'
import FAQ from '../components/FAQ.vue'

import BowlingImg from '../assets/img/Bowling.webp'
import GokartImg from '../assets/img/Gokart.webp'
import LasergameImg from '../assets/img/Lasergame.webp'
import LegelandImg from '../assets/img/Legeland.webp'
import SpillehalImg from '../assets/img/Spillehal.webp'
import VirtualrealityImg from '../assets/img/VirtualReality.webp'
import VREscapeImg from '../assets/img/VREscape.webp'

const cards = [
  { title: 'Bowling', description: 'Hvis du er til bowling, så er Action House stedet. Oplev sjov bowling for hele familien i vores bowlingcenter.', image: BowlingImg },
  { title: 'Gokart', description: 'Danmarks fedeste indendørs gokartbane. Oplev høj fart på vores indendørs gokartbane, som er en af Danmarks længste baner!', image: GokartImg },
  { title: 'Lasergame', description: 'Prøv Laser Maxx Lasergame i Action House. En sjov oplevelse for hele familien, venner eller kolleger', image: LasergameImg },
  { title: 'Legeland', description: 'Stort legeland hvor børnene kan have det sjovt. Hos Action House har vi et legeland for børn i alle aldre.', image: LegelandImg },
  { title: 'Spillehal', description: 'I Action House har vi udover alle vores andre attraktioner en spillehal med bl.a. Pool, Billiard, Air-hockey og meget mere', image: SpillehalImg },
  { title: 'Virtual Reality', description: 'Stort VEX Virtual Reality Arena. Kom til Action House og oplev vores super sjove VR Arena og nedkæmp zombier med venner og familie.', image: VirtualrealityImg },
  { title: 'VR Escaperoom', description: 'Tag de virtuelle briller og udstyr på og bevæg dig på mission med vennerne, familien eller kollegaerne på vores nye Vex Virtuel Reality Escaperoom.', image: VREscapeImg }
]

const slugify = title =>
  title.toLowerCase().replace(/\s+/g, '-')
</script>

<template>
  <Header />

  <img src="../../assets/img/Gokart.webp" alt="Gokart i action house" class="hero-video" />

  <div class="aktiviteterWrapper">
    <section class="aktIntro">
      <h1 class="aktOverskrift">Aktiviteter</h1>
      <p class="aktParagraph">
        Hos Action House Funcenter finder du et bredt udvalg af actionfyldte og sjove aktiviteter for både børn, unge og voksne.
        Uanset om du er til fart, konkurrence eller hyggeligt samvær, har vi oplevelser, der passer til enhver anledning.
        Gå på opdagelse i vores aktiviteter herunder, og find den næste oplevelse, der sætter gang i adrenalinen og skaber minder.
      </p>
    </section>

    <section class="flip-grid">
      <div
        v-for="(card, index) in cards"
        :key="index"
        class="flip-card"
      >
        <div class="flip-card-inner">
          <div class="flip-card-front">
            <img :src="card.image" alt="" />
            <div class="front-overlay">
              <div class="text-background"></div>
              <h3>{{ card.title }}</h3>
            </div>
            <div class="flip-icon">↻</div>
          </div>
          <div class="flip-card-bagside">
            <div>
              <p>{{ card.description }}</p>
              <NuxtLink
                :to="`/aktiviteter/${slugify(card.title)}`"
                class="read-more-link"
              >
                Læs mere om {{ card.title }}
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>

  <FAQ />
  <Footer />
</template>

<style>
.hero-video {
  width: 100vw;
  height: 50vh;
  object-fit: cover;
  object-position: center 20%;
  margin: 0;
  display: block;
}

.flip-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  padding: var(--NormPadding);
  max-width: 100%;
  margin: 0 auto;
}

.aktiviteterWrapper {
  margin-left: 8.65625rem;
  margin-right: 8.65625rem;
}

.flip-card {
  height: 420px;
  perspective: 1000px;
}

.flip-card-inner {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.8s;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-bagside {
  position: absolute;
  inset: 0;
  border-radius: 12px;
  backface-visibility: hidden;
  overflow: hidden;
}

.flip-card-front img {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.front-overlay {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items: center;
  padding: 0.5rem;
}

.text-background {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 100px;
  background: rgba(255, 255, 255, 0.6);
  border-radius: 0 0 12px 12px;
}

.front-overlay h3 {
  margin: 0;
  font-size: 1.7rem;
  color: #154B82;
  padding-left: 0.5rem;
  position: absolute;
  transform: translateY(-100%);
}

.flip-icon {
  position: absolute;
  bottom: 0.5rem;
  right: 0.5rem;
  font-size: 2.2rem;
  color: white;
  opacity: 0.8;
}

.flip-card-bagside {
  background: white;
  transform: rotateY(180deg);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem;
  color: black;
  text-align: center;
}

.read-more-link {
  display: inline-block;
  margin-top: 1rem;
  color: #154B82;
  text-decoration: underline;
  font-weight: 500;
}

.read-more-link:hover {
  color: #cc1824;
}

.aktOverskrift {
  text-align: center;
  margin-top: 2rem;
  color: #154B82;
}

.aktParagraph {
  text-align: center;
  margin: 2rem 20rem;
  color: #154B82;
}

.aktIntro {
  max-width: 100%;
}

@media (max-width: 600px) {
  .flip-grid {
    grid-template-columns: repeat(2, 1fr);
    margin: 0 1rem;
  }
  .aktiviteterWrapper {
    margin-left: 1rem;
    margin-right: 1rem;
  }
  .aktParagraph {
    margin: 1rem;
  }
  .flip-card {
    height: 20rem;
  }
  .flip-card-bagside p {
    font-size: 0.9rem;
    line-height: 1.3;
  }
  .front-overlay h3 {
    font-size: 1.2rem;
  }
}
</style>
