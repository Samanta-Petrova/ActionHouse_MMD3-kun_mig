<script setup>
import { ref } from 'vue'


const timeline = ref(1)

const nextStep = () => {
    if(timeline.value < 4) timeline.value++
}
const prevStep = () => {
    if(timeline.value > 1) timeline.value--
}


</script>

<template>
<div>
    <div class="timelines">
        <span :class="{ active: timeline === 1 }">1994</span>
        <span :class="{ active: timeline === 2 }">2000</span>
        <span :class="{ active: timeline === 3 }">2010</span>
        <span :class="{ active: timeline === 4 }">2016</span>
    </div>
    <h2>Vores historie</h2>
    <div class="timelineContainer" v-if="timeline === 1">
        <p>1994: Action House åbner i de gamle RC Caravans-bygninger med indendørs gokart og bowling - det første kombinerede Funcenter i Danmark.</p>
        <p>1995: Udvidelse med et af Nordens største diskoteker og lasergame inspireret af New York.</p>
        <p>1997: Indendørs paintballbane etableres.</p>
        <button @click="nextStep">næste</button>
    </div>
    <div class="timelineContainer" v-if="timeline === 2">
        <p>2000: Drive-in biograf åbner.</p>
        <p>2005: Stormen rammer, taget blæser af, centeret lukker i 4 måneder.</p>
        <p>2007-2009: Gokartbanen udvides, kurvesvinget etableres, bar og spillehal flyttes, og 2 ekstra bowlingbaner opføres.</p>
        <button @click="prevStep">tilbage</button>
        <button @click="nextStep">næste</button>
    </div>
    <div class="timelineContainer" v-if="timeline === 3">
        <p>2010: Legeland på 200 m² for børn 0-12 år, inkl. område for de mindste.</p>
        <p>2012-2015: Nyt lasergame-udstyr med op til 6 hold, udvidet med 300 m² labyrint og nye spilmuligheder.</p>
        <p>2013: Solceller producerer nu 50% af vores strømforbrug (ca. 160.000 kWh årligt).</p>
        <p>2013/2014: Introduktion af skydesimulator.</p>
        <p>2015: Lasergame udvides til 600 m², nu en af Danmarks største baner.</p>
        <button @click="prevStep">tilbage</button>
        <button @click="nextStep">næste</button>
    </div>
    <div class="timelineContainer" v-if="timeline === 4">
        <p>2016-2017: “Den hjemsøgte labyrint” til Halloween, og gokartbanen udvides med 4.500 m², nu verdens største med 1,1 km bane og 32 gokarts samtidig.</p>
        <p>2019: Paintballbanen nedlægges til fordel for VEX VR arena.</p>
        <p>2024/2025: Stort legeland på 1.250 m² klar i 2025</p>
        <button @click="prevStep">tilbage</button>
    </div>
    
</div>
</template>

<style scoped>

.timelines{
    display: flex;
    gap: 10px;
    justify-content: space-evenly;
}

.timelines span{
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: var(--mainblue);
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 50px;
    color: white;
}

h2{
    text-align: center;
    color: var(--mainblue);
}

.timelineContainer{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    margin: 100px 100px;
}
</style>