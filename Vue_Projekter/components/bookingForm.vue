<script setup>
import { ref } from 'vue';

// steps
// en variabel der viser hvilket step du er inde på og gemmer det indhold som ligger under hvert step den er sat til 1 så den starter på det rigtige step. 
const step = ref(1)

// steps data
const formData = ref({
    name: '',
    lastName: '',
    email: '',
    telefonNr: '',
    date: '',
    time:'',
    antalDeltagere: '',
})



// navigere steps
// via en if statement kan funktionen læse hvad værdien den span den står på og hvis den værdi er mindre en syv kan den ligge et tal oven i og navigere videre til den den næste span som har en value der er en højere. den skal ikke kunne gå over 7 fordi der ikke er flere steps i booking formularen
const nextStep = () => {
    if (step.value < 7) step.value++
}

// samme som funktionen oven over ved at en if statement kan den læse valuen af den span den står på og hvis værdien er højere end 1 kan trække et tal fra og på den måde navigere en span tilbage vha. at læse den næste spans value
const prevStep = () => {
    if (step.value > 1) step.value--
}

// submit form
// en funktion der logger den data som bliver sat ind i formdata objektet med v-model og sender det ind i consolen. 
const sumbitForm = () => {
    console.log("Din booking er nu insendt!", formData.vaule)
}

// dropdown til tilbudspakker
const valgtTilbud = ref("") 

const tilbudspakker = [
    "Action (10min Gokart, 12min Lasergame, 57min Bowling)",
    "Lux Action(25min Gokart, 20min Lasergame, 57min Bowling)",
    "Mega Action(55min Gokart, 30min Lasergame, 117min Bowling)",
    "Formel 1(25min Gokart inkl. (15mins tidstagning, 10min Finale))",
    "Lux Formel 1(50min Gokart inkl. (25min tidstagning, 25min Finale))",
    "Leman (50min holdkørsel - min 16 hold)",
    "Herre Aften (25min Gokart, 57min Bowling, skydesimulator)",
    "Dame aften (20min Lasergame, 57min Bowling, skydesimulator)",
    "Blå Mandags pakke",
    "Julefrokost",
    "Spis & Bowl(spisning, 57min Bowling)",
    "Børnefødselsdag",
    "Vr Action pakke(10min Gokart, 12min VR, 12min Lasergame)",
    "Lux VR Action pakke(24min VR, 25min Gokart, 20min Lasergame)"
]

// liste over aktiviteter
const valgtAktivitet = ref([]) 

const aktiviteter = [
  "Bowling",
  "10min Gokart",
  "15min Gokart",
  "Formel 1(gokart 25min)",
  "Lux Formel 1(gokart 50min)",
  "12min Lasergame",
  "20min Lasergame",
  "30min Lasergame",
  "Legeland",
  "30min skydesimulator",
  "60min skydesimulator",
  "12min Virtuel reality (min 12 år)",
  "24min Virtuel reality (min 12 år)"
]
// liste over spisemuligheder
const valgtSpiseOpt = ref([]) 

const spiseOpt = [
  "forret",
  "hovedret",
  "buffet",
  "frisoftice til buffet",
  "dessert"
]

// list over steder folk kan have hørt om action house

const valgtLokation = ref([])

const lokationer = [
  "Google",
  "Facebook",
  "Instagram",
  "Youtube",
  "TikTok",
  "Radio",
  "Familie/Venner/Kollegaer",
  "Avis",
  "Internettet",
  "løkken.dk",
  "blokhus.dk",
  "visit Nordvestkysten",
  "tv"
]

// dette er variabler som søger for at det indhold der ligger inde i checkbox div'en ikke bliver vist med mindre man chekker boxen af i grænsefalden. 
const visAktivitet = ref(false)
const visTilbud = ref(false)
</script>

<template>
 <div class="booking-form">
<!-- dette er vores progress bar som fungere på den måde at du har en span med active class. hver span har fået tildelt en value det matcher med den div med samme value. der indholder det data som passer ind i den del af progress baren. det virker på den måde at den kan navigere imellem de andre spans, via deres value som forklaret i funktionerne oven over. hver span passer til et step i bookingformularen-->
    <div class="steps">
      <span :class="{ active: step === 1 }">1</span>
      <span :class="{ active: step === 2 }">2</span>
      <span :class="{ active: step === 3 }">3</span>
      <span :class="{ active: step === 4 }">4</span>
      <span :class="{ active: step === 5 }">5</span>
      <span :class="{ active: step === 6 }">6</span>
      <span :class="{ active: step === 7 }">7</span>
    </div>

    <!-- Step 1 person oplysninger-->
    <!-- en if statement der gør at vis steps value er = 1 skal den render dette indhold -->
    <div class="step" v-if="step === 1">
      <div class="personoplysninger">
        <h2>Person Oplysninger</h2>
        <label for="fornavn">Fornavn</label>
        <br>
        <input type="text" placeholder="fornavn" v-model="formData.name" />
        <br>
        <label for="efternavn">Efternavn</label>
        <br>
        <input type="text" placeholder="efternavn" v-model="formData.lastName" />
        <br>
        <label for="Email">Email</label>
        <br>
        <input type="email" placeholder="ActionHouse@actionhouse.dk" v-model="formData.email">
        <br>
        <label for="telefon">Telefon nr</label>
        <br>
        <input type="tel" placeholder="+45 00 00 00 00" v-model="formData.tel">
        <button @click="nextStep">Næste</button>
      </div>
    </div>

    <!-- Step 2 dato og tid-->
    <div class="step" v-if="step === 2">
      <div class="datoOgTid">
        <h2>Dato og Tid</h2>
        <label for="dato">Dato</label>
        <br>
        <input type="date" v-model="formData.date">
        <br>
        <label for="time">Tidspunkt</label>
        <br>
        <input type="time" v-model="formData.time">
        <br>
        <label for="Deltager">Antal Deltager</label>
        <br>
        <input type="text" v-model="formData.antalDeltagere">
        <div>
            <button @click="prevStep">Tilbage</button>
            <button @click="nextStep">Næste</button>
        </div>
      </div>
    </div>

    <!-- Step 3 vælg aktiviteter-->
    <div class="step" v-if="step === 3">
      <div>
        <h2>Valg af Aktivitet</h2>
        <div class="checkboxContainer">
          <div>
            <label for="vælgTilbudspakker">tilbudspakker</label>
            <input type="checkbox" id="vælgTilbudspakke" v-model="visTilbud">
            <br>
            <br>
            <select v-if="visTilbud" name="vælgTilbudspakker" id="vælgTilbudspakker" v-model="valgtTilbud">
              <option disabled value="">Vælg et tilbud</option>
              <option v-for="tilbudspakke in tilbudspakker" :key="tilbudspakke" >{{ tilbudspakke }}</option>
            </select>
          </div>
          <div> 
            <label for="vælgAktiviteter">Aktiviteter</label>
            <!-- Checkbox der viser/skjuler listen --> 
            <input type="checkbox" id="vælgAktivitet" v-model="visAktivitet">
            <!-- Liste over aktiviteter --> 
            <div v-if="visAktivitet"> 
              <div v-for="aktivitet in aktiviteter" :key="aktivitet">
              <input type="checkbox" :id="aktivitet" v-model="valgtAktivitet" > 
              <label :for="aktivitet">{{ aktivitet }}</label> 
            </div> 
          </div> 
        </div>
        </div>
      <div>
          <button @click="prevStep">Tilbage</button>
          <button @click="nextStep">næste</button>
      </div>
      </div>
    </div>
    <!-- step 4 spisning-->
    <div class="step" v-if="step === 4">
      <h2>Spisning</h2>
      <div class="spisningContainer">
        <div v-for="food in spiseOpt" :key="food" class="foodContainer">
          <input type="Checkbox" :id="food" v-model="valgtSpiseOpt">
          <label :for="food">{{ food }}</label>
        </div>
      </div>
      <div>
        <button @click="prevStep">tilbage</button>
        <button @click="nextStep">Næste</button>
      </div>
    </div>
    <!-- step 5 deltagerliste -->
    <div class="step" v-if="step === 5">
      <h2>deltagerliste</h2>
      <input type="text" class="deltagerListe">
      <div>
        <button @click="prevStep">tilbage</button>
        <button @click="nextStep">næste</button>
      </div>
    </div>
    <div class="step" v-if="step === 6">
      <h2>Hvor fik du inspiration til Booking</h2>
      <div class="lokationContainer">
        <div v-for="lokation in lokationer">
          <input type="checkbox" class="lokationCheckbox" :id="lokation"  v-model="valgtLokation">
          <label :for="lokation">{{ lokation }}</label>
        </div>
      </div>
      <div>
        <button @click="prevStep">tilbage</button>
        <button @click="nextStep">næste</button>
      </div>
    </div>
    <div class="step" v-if="step === 7">
      <h2>kommentarer</h2>
      <div class="kommentarerContainer">
        <input type="text">
        <div class="godkendContainer">
          <h3>tilmeld nyhedsbrev</h3>
          <input type="checkbox">
          <label for="nyhedsbrev">ja tak</label>
        </div>
        <div class="godkendContainer">
          <h3>Persondata godkendelse</h3>
          <p>Jeg godkender hermed at Action House Løkken må bruge de ovenfor indtastede oplysninger i forbindelse med booking af aktiviteter. Action House bruger udelukkende disse oplysninger for at kunne foretage en booking af valgte aktiviterer. Yderligere oplysninger kan findes i vores privatlivspolitik</p>
          <input type="checkbox">
          <label for="godkendelse">jeg godkender betingelserne</label>
        </div>
      </div>
      <div>
        <button @click="prevStep">tilbage</button>
        <button @click="sumbitForm">Book</button>
      </div>
    </div>
 </div>

 <!-- value="tilbudspakke"- value="lokation" - value="food" - value="aktivitet" -->
</template>

<style scoped>
.steps {
  display: flex;
  gap: 10px;
  justify-content: space-evenly;
}

.steps span {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #ddd;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 2rem;
}
.steps .active {
  background: var(--mainblue);
  color: white;
}

input[type=text]{
    max-width: 500px;
    min-width: 50px;
    height: 2rem;
}
input[type=email]{
    max-width: 500px;
    min-width: 50px;
    height: 2rem;
}
input[type=tel]{
    max-width: 500px;
    min-width: 200px;
    height: 2rem;
}

input[type=checkbox]{
  transform: scale(1.8);
}

.step{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.personoplysninger{
  display: flex;
  flex-direction: column;
}
.datoOgTid{
  display: flex;
  flex-direction: column;
}

.step button{
    width: 100px;
    margin: 1rem;
    justify-content: space-between;
    align-items: flex-end;
}

button{
  background: var(--mainblue);
  color: white;
  border-radius: 5px;
  border-color: none;
  padding: 8px;
  font-size: 1.2rem;
}


.checkboxContainer { 
  display: flex;
  gap: 15px; 
  padding: 20px; 
  justify-content: space-between;
}


.checkboxContainer input[type="checkbox"] { 
  margin-right: 10px;  
  border: 3px solid red;
  } 
    
.checkboxContainer select { 
  padding: 10px 12px; 
  background: white; 
  font-size: 15px; 
} 
.spisningContainer { 
  display: flex;
  gap: 15px; 
  padding: 20px; 
  justify-content: space-evenly;
  flex-direction: column;
  
}


.spisningContainer input[type="checkbox"] { 
  margin-right: 10px;  
  width: 50px;
  } 
 

/* .deltagerListe{
  width: 300px;
  height: 200px;
} */

.lokationContainer { 
  display: flex;
  gap: 15px; 
  padding: 20px; 
  justify-content: space-evenly;
  flex-direction: column;
}


.lokationContainer .lokationCheckbox { 
  margin-right: 10px;  
  width: 50px;
  } 
  

.kommentarerContainer input{
  padding-right: 200px;
  padding-bottom: 100px;
}


.godkendContainer input[type="checkbox"] { 
  margin-right: 10px;  
  width: 50px;
  } 

.godkendContainer p{
  width: 50ch;
  font-size: 0.9rem;
}


@media (max-width: 400px) {

  .steps span {
  width: 40px;
  height: 40px;
}

.step h2{
  font-size: 1.5rem;
}

.lokationContainer{
  justify-content: flex-start;
}

.lokationContainer label{
  font-size: 0.9rem;
}

.lokationContainer .lokationCheckbox{
  width: 100px;
  margin: 0;
}


.step button{
    width: 100px;
    font-size: 1rem;
    margin: 1rem;
    justify-content: space-between;
    align-items: center;
}

}

</style>