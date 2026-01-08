<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue' // Her importere vi de forskellige funktioner vi skal bruge fra Vue biblioteket

// Importere billeder vi skal bruge til flipcards
import BowlingImg from '../assets/img/Bowling.webp'
import GokartImg from '../assets/img/Gokart.webp'
import LasergameImg from '../assets/img/Lasergame.webp'
import Legeland from '../assets/img/Legeland.webp'
import Spillehal from '../assets/img/Spillehal.webp'
import Virtualreality from '../assets/img/VirtualReality.webp'
import VREscape from '../assets/img/VREscape.webp'

// Definerer værdier i et array som vi kan bruge til at generere flipcards
const baseCards = [
  { title: 'Bowling', caption: 'Sjov for alle', description: 'Tag venner og familie med til bowling i moderne baner.', image: BowlingImg },
  { title: 'Gokart', caption: 'Fart og spænding', description: 'Oplev høj fart på vores indendørs gokartbane.', image: GokartImg },
  { title: 'Lasergame', caption: 'Action og taktik', description: 'Kæmp mod vennerne i vores lasergame arena.', image: LasergameImg },
  { title: 'Spillehal', caption: 'Spillehal til familien', description: 'Nyd sjove arkadespil i spillehalen', image: Spillehal },
  { title: 'Legeland', caption: 'Legeland til børn', description: 'Sjov og leg for de mindste.', image: Legeland },
  { title: 'Virtual Reality', caption: 'Virtual reality', description: 'Oplev VR i verdensklasse.', image: Virtualreality },
  { title: 'VR Escaperoom', caption: 'Firma og grupper', description: 'Perfekt til firmaevents og grupper.', image: VREscape }
]

// Definerer antal kort per side og antal sider i carousel (3*3=9 kort vist)
const cardsPerPage = 3
const pages = 3

// Generere kortene til carousel ved at gentage baseCards indtil vi har nok kort til alle sider
const cards = computed(() => {
  const result = [...baseCards]
  while (result.length < cardsPerPage * pages) {
    result.push(baseCards[result.length % baseCards.length])
  }
  return result
})

// Holder styr på hvilken side der er aktiv i carousel for autoplay funktionalitet
const activePage = ref(0)
const track = ref(null)
let interval = null

// Starter autoplay funktionen som skifter side hver 5. sekund
const startAutoplay = () => {
  if (interval) return
  interval = setInterval(() => {
    activePage.value = (activePage.value + 1) % pages
    scrollToPage(activePage.value)
  }, 5000)
}
// Stopper autoplay funktionen
const stopAutoplay = () => {
  clearInterval(interval)
  interval = null
}

// Funktion til at scrolle til en bestemt side i carousel via. dots navigation
const scrollToPage = page => {
  activePage.value = page
  const cardWidth = track.value.children[0].offsetWidth
  track.value.scrollTo({
    left: cardWidth * cardsPerPage * page,
    behavior: 'smooth'
  })
}

// Her starter vi autoplay funktionen så snart komponentet er sat ind i DOM'en

onMounted(() => {
  startAutoplay()
})
// Stopper den igen når komponentet fjernes fra DOM'en, altså når den ikke længere vises
onUnmounted(() => {
  stopAutoplay()
})
</script>

<template>
  <section class="carousel" @mouseenter="stopAutoplay" @mouseleave="startAutoplay">
    <div class="track" ref="track">
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
            <p>{{ card.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <div class="dots">
      <span
        v-for="i in pages"
        :key="i"
        :class="{ active: i - 1 === activePage }"
        @click="scrollToPage(i - 1)"
      />
    </div>
  </section>
</template>

<style scoped>
.carousel {
  width: 100%;
  overflow: hidden;
  padding: var(--NormPadding);
}

.track {
  display: flex;
  gap: 2rem;
  overflow-x: hidden;
  scroll-behavior: smooth;
}

.flip-card {
  flex: 0 0 300px;
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
  z-index: 1;
}

.front-overlay h3 {
  margin: 0;
  font-size: 1.7rem;
  color: #154B82;
  padding-left: 0.5rem;
  z-index: 2;
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
  z-index: 2;
  transform: translateX(-10%);
}

.flip-card-bagside {
  background: white;
  transform: rotateY(180deg);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem;
  color: black;
}

.dots {
  display: flex;
  justify-content: center;
  margin-top: 1rem;
  gap: 0.5rem;
}

.dots span {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: #154B82;
  cursor: pointer;
}

.dots span.active {
  background: #D41E2A;
}

@media (max-width: 400px) {
  .track {
    overflow-x: auto;
    gap: 1rem;
  }
  .flip-card {
    flex: 0 0 200px;
    height: 280px;
  }
  .flip-card-front img {
    object-fit: cover;
  }
}
</style>
