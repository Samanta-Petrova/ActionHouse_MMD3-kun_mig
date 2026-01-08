<script setup>
import { ref } from 'vue';

// steps
// en variabel der viser hvilket step du er inde på og gemmer det indhold som ligger under hvert step den er sat til 1 så den starter på det rigtige step. 
const step = ref(1)

// steps data
const formData = ref({
    name: "",
    lastName: "",
    email: "",
    telefonNr: "",
    date: "",
    time:"",
    antalDeltagere: "",
})



// navigere steps
// en if statement der læser step value og hvis den value er under syv ligger 1 tal oven i steps value
const nextStep = () => {
    if (step.value < 7) step.value++
}

// samme funktion som oven over en funktion med en if statement der kan læse step value og hvis værdien er over 1 kan den trække 1 fra steps value
const prevStep = () => {
    if (step.value > 1) step.value--
}

// submit form
// en funktion der logger den data som bliver sat ind i formdata objektet med v-model og sender det ind i consolen. 
const sumbitForm = () => {
    console.log("Din booking er nu insendt!", formData.vaule)
}

// dropdown til tilbudspakker
// en variabel der binder det valgt tilbud ind i variablen som du vælger nede i select via v-model
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
// en variabel der gemmer de valg du klikker af i checkboxen via v-model binder den dine valg ind i en liste som gemmer de valg
const valgtAktivitet = ref([]) 

// et arrat med enkelte aktiviteter
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
// en variabel der gemmer de valg du klikker af i checkboxen via v-model binder den dine valg ind i en liste som gemmer de valg
const valgtSpiseOpt = ref([]) 

// et array med spise muligheder
const spiseOpt = [
  "forret",
  "hovedret",
  "buffet",
  "frisoftice til buffet",
  "dessert"
]

// list over steder folk kan have hørt om action house

// en variabel der gemmer de valg du klikker af i checkboxen via v-model binder den dine valg ind i en liste som gemmer de valg
const valgtLokation = ref([])

// et array over de forskellige lokationer
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
  "Løkken.dk",
  "Blokhus.dk",
  "Visit Nordvestkysten",
  "TV"
]

// dette er variabler som søger for at det indhold der ligger inde i checkbox div'en ikke bliver vist med mindre man chekker boxen af i grænsefalden.
const visAktivitet = ref(false)
const visTilbud = ref(false)
</script>

<template>
 <div class="booking-form">
<!-- dette er vores progress bar som fungere på den måde at du har en span som har fået tildelt et objekt og hvis valuen matcher med den value step har skal denne span have classen active. via dynamisk binding binder den active class ind på span 1 hvis step value er = 1-->
    <div class="steps">
      <span :class="{ active: step === 1 }">1</span>
      <span :class="{ active: step === 2 }">2</span>
      <span :class="{ active: step === 3 }">3</span>
      <span :class="{ active: step === 4 }">4</span>
      <span :class="{ active: step === 5 }">5</span>
      <span :class="{ active: step === 6 }">6</span>
      <span :class="{ active: step === 7 }">7</span>
    </div>

    <!-- Step 1 valg af aktivitet-->
     <div class="step" v-if="step === 1">
        <h2>Valg af Aktivitet</h2>
        <div class="checkboxContainer">
          <div>
            <div class="checkboxValg">
              <label for="vælgTilbudspakker">Tilbudspakker</label>
              <!-- en check box som har en default værdi på false og når den bliver tjekket af ændre værdien sig til true -->
              <input type="checkbox" id="vælgTilbudspakke" v-model="visTilbud">
            </div>
            <!-- hvis værdien er true i variablen vistlbud skal den vise den select i DOM'en hvis ikke skal den er false skal den ikke renders -->
            <select v-if="visTilbud" name="vælgTilbudspakker" id="vælgTilbudspakker" v-model="valgtTilbud">
              <!-- viser den tomme værdi når man ikke har valgt noget -->
              <option disabled value="">Vælg et tilbud</option>
              <!-- en for each statement der laver en option for hver af de strings som er gemt i arrayet tilbudspakker -->
              <option v-for="tilbudspakke in tilbudspakker" :key="tilbudspakke" >{{ tilbudspakke }}</option>
            </select>
          </div>
          <div> 
            <div class="checkboxValg">
              <label for="vælgAktiviteter">Aktiviteter</label>
              <!-- Checkbox der viser/skjuler listen --> 
              <input type="checkbox" id="vælgAktivitet" v-model="visAktivitet">
            </div>
          <!-- hvis værdien er true i variablen vistlbud skal den vise den select i DOM'en hvis ikke skal den er false skal den ikke renders -->
            <div v-if="visAktivitet"> 
              <div v-for="aktivitet in aktiviteter" :key="aktivitet" class="singleAktivitet">             
                  <input type="checkbox" :id="aktivitet" v-model="valgtAktivitet" > 
                  <label :for="aktivitet">{{ aktivitet }}</label> 
              </div> 
          </div> 
        </div>
        </div>
        <div>
          <button @click="nextStep">næste</button>
        </div>         
    </div>
    <!-- en if statement der gør at vis steps value er = 1 skal den render dette indhold -->
    

    <!-- Step 2 spisning-->
    <div class="step" v-if="step === 2">
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
    
 
    <!-- Step 4 person oplysninger-->
    <div class="step" v-if="step === 3">
      <div class="personoplysninger">
        <h2>Person Oplysninger</h2>
        <label for="fornavn">Fornavn</label>
        <br>
        <!-- v-model binder den data som bliver inputet i fornavns feltet ind i formdata vairablen fornavn og gemmer den data så den kan blive sendt ind i consolen -->
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
        <div>
          <button @click="prevStep">Tilbage</button>
          <button @click="nextStep">Næste</button>
        </div>
      </div>
    </div>

    <!-- step 5 dato og tid-->
    <div class="step" v-if="step === 4">
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
          <!-- en knap med et en eventlistener der lytter efter et click. når en bruger klikker på knappen næste (funktionen nextStep) ligger den et tal oven i step value og når man klikker på og man klikker på tilbage (funktionen prevStep trækker den et tal fra step value) på den måde kan du navigere i gennem de forskellige div fordi de hver især har en if statement der fortæller at den skal render indholdet hvis diven har samme value som step. -->
            <button @click="prevStep">Tilbage</button>
            <button @click="nextStep">Næste</button>
        </div>
      </div>
    </div>
    
    <!-- step 3 deltagerliste -->
    <div class="step" v-if="step === 5">
      <h2>deltagerliste</h2>
      <p>(kun nødvendigt til bowling, gokart eller lasergame)</p>
      <textarea name="deltagerListe" id="deltagerliste" rows="10" cols="50"></textarea>
      <p>Skriv deltagernavne her - Så er navnene skrevet ind når i kommer.</p>
      <div>
        <button @click="prevStep">tilbage</button>
        <button @click="nextStep">næste</button>
      </div>
    </div>

    <!-- step 6 inspiration til booking -->
    <div class="step" v-if="step === 6">
      <h2>Hvor fik du inspiration til Booking</h2>
      <div class="lokationContainer">
        <!-- for each statement der skaber en checkbox og label for hver string der er gemt i variablen lokationer -->
        <div v-for="lokation in lokationer">
          <!-- v-model binder vaulen fra checkboxen sammen med den variable der hedder valgtlokation som er dynmasik.  -->
          <input type="checkbox" class="lokationCheckbox" :id="lokation"  v-model="valgtLokation">
          <!-- {{ lokation viser alle de muligheder de muligheder der er at vælge i mellem.  }} -->
          <label :for="lokation">{{ lokation }}</label>
        </div>
      </div>
      <div>
        <button @click="prevStep">tilbage</button>
        <button @click="nextStep">næste</button>
      </div>
    </div>
    <!-- step 7 kommentarer -->
    <div class="step" v-if="step === 7">
      <h2>kommentarer</h2>
      <div class="kommentarerContainer">
        <textarea name="kommentarfelt" id="kommentarfelt" rows="10" cols="50"></textarea>
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


.step input{
  width: 100%;
  max-width: 500px;
  font-size: 1.1em;
}

.step input[type=checkbox]{
  transform: scale(1.8);
}

.step select{
  width: 100%;
  max-width: 500px;
}

.step option{
  width: 100%;
  max-width: 500px;
}

.step label{
  font-size: 1.2rem;
}

.step h3{
  font-size: 1.5rem;
}

.step p{
  font-size: 1.3rem;
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
  flex-direction: row;
  gap: 15px; 
  padding: 20px; 
  justify-content: space-evenly;
}

.checkboxContainer input[type="checkbox"] { 
  margin-right: 10px;  
  border: 3px solid red;
  } 
    
.checkboxContainer select { 
  margin-top: 1rem;
  padding: 10px 12px; 
  background: white; 
  font-size: 1rem; 
} 

.checkboxValg{
  display: flex;
  align-items: center;
  gap: 10px;
}

.singleAktivitet{
  display: flex;
  align-items: center;
  gap: 10px;
}

.singleAktivitet input[type="checkbox"]{
  max-width: 50px;
  padding-bottom: 0.5rem;
}

.singleAktivitet label{
  width: 400px;
  padding-bottom: 0.5rem;
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
}



@media (max-width: 400px) {

.steps span {
  width: 40px;
  height: 40px;
}

.step{
  margin: 1rem 1rem 1rem 1rem;
}
.step h2{
  font-size: 1.5rem;
}

.step p{
  font-size: 0.9rem;
}

.step label{
  font-size: 1rem;
}


.step button{
    width: 100px;
    font-size: 1rem;
    margin: 1rem;
    justify-content: space-between;
    align-items: center;
}

.lokationContainer{
  width: 100%;
  max-width: 300px;
  padding: 0;
}

.checkboxContainer{
  gap: 5rem;
  padding: 0;
}

.checkboxContainer select {
  margin-top: 1rem;
  margin-left: 0rem;
  padding: 10px 12px; 
  background: white; 
  font-size: 0.7rem; 
} 


.godkendContainer p{
  width: 40ch;
  font-size: 0.9rem;
}

.godkendContainer textarea{
  margin-left: 10px;
}

.godkendContainer h3{
  font-size: 1.3rem;
}



}

</style>