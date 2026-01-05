<script setup>
import Header from '../components/navigation.vue'
import FlipCards from '../components/FlipCards.vue'
import Galleri from '../components/Galleri.vue'
import Footer from '../components/Footer.vue'
</script>

<template>
  <Header />

  <main>
    <video
      class="hero-video"
      autoplay
      muted
      loop
      playsinline
    >
      <source src="../assets/vid/Action-house-1.1-II-_1_-_1_.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <section>
      <h1 class="forsideTitles">Sjov og action for alle</h1>
      <p class="forsideParagraphs forsideMaxLength">
        Hos Action House i Løkken finder du et væld af sjove aktiviteter og oplevelser fordelt på 12.530 m².
        Længere nede på siden kan du læse om historien bag Action House Funcenter samt se en tidslinje for,
        hvornår vores forskellige forlystelser blev etableret. Vi tilbyder sjove og unikke oplevelser for
        både børn og voksne.
      </p>
    </section>

    <FlipCards />

    <h2 class="forsideTitles">Om os</h2>

    <section class="omOsSection">
      <div class="omOsContainer">
        <div class="omOsText">
          <p class="forsideParagraphs">
            Action House Funcenter er stedet, hvor fart, fællesskab og sjove oplevelser mødes.
            Uanset om du kommer for at konkurrere, grine eller skabe minder med venner, familie
            eller kolleger, har vi rammerne til en dag fyldt med action.
            <br><br>
            Læs mere på <a href="#">Om os.</a>
          </p>
        </div>

        <div class="omOsImage">
          <img src="../assets/img/actionhouseFacade.webp" alt="">
        </div>
      </div>

      <button class="forsideButton">Læs mere</button>
    </section>

    <section>
      <h2 class="forsideTitles">Galleri</h2>
      <Galleri />
    </section>
  </main>

<Footer />

</template>

<style scoped>
.hero-video {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.forsideTitles {
  text-align: left;
  margin-top: 2rem;
  margin-left: 2rem;
  color: #154B82;
}

.forsideParagraphs {
  text-align: left;
  margin-top: 1rem;
  margin-left: 2rem;
  margin-right: 2rem;
  margin-bottom: 2rem;
}

.forsideMaxLength {
  max-width: 50%;
}

.omOsSection {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  margin-bottom: 2rem;
}

.omOsContainer {
  display: flex;
  flex-direction: row;
  max-width: 80%;
  gap: 2rem;
  margin-bottom: 2rem;
}

.omOsText {
  flex: 1;
}

.omOsImage {
  flex: 1;
}

.omOsImage img {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.forsideButton {
  padding: 0.75rem 2.5rem;
  background-color: #D41E2A;
  color: #ffffff;
  border: none;
  border-radius: var(--desktopBorder);
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.5s ease;
}

.forsideButton:hover {
  background-color: #154B82;
}

img {
  border-radius: var(--desktopBorder);
}
</style>
