<script setup>
import navigation from '~/components/navigation.vue';
import Footer from '../components/Footer.vue'
</script>

<template>
<Navigation></Navigation>
<section>
    <article>
        <img src="../assets/img/kontaktHeader.png" alt="billeder af mennesker med gokart hjelm">
    </article>
</section>
<section class="kontaktContainer">
    <article class="kontaktInfo">
        <h2>Kontakt</h2>
        <a href="tel:+4599676710">Telefon +45 99 67 67 10</a>
        <br>
        <a href="mailto:info@actionhouse.dk">Email: info@actionhouse.dk</a>     
        <div class="socialContainer">    
            <h2>Følg os på:</h2>
            <div>
                <img src="../assets/img/facebook-logo.svg" alt="facebook logo">
                <img src="../assets/img/X-logo.svg" alt="x logo">
            </div>
        </div>
    </article>
    <article class="kontaktDato">
        <h2>Åbningstider</h2>
        <div class="datoOgTid">
            <div>
                <p>Mandag</p>
                <p>Tirsdag</p>
                <p>Onsdag</p>
                <p>Torsdag</p>
                <p>Fredag</p>
                <p>Lørdag</p>
                <p>Søndag</p>
            </div>
            <div>
                <p>10:00 - 22:00</p>
                <p>10:00 - 22:00</p>
                <p>10:00 - 22:00</p>
                <p>10:00 - 22:00</p>
                <p>10:00 - 00:00</p>
                <p>10:00 - 00:00</p>
                <p>10:00 - 22:00</p>
            </div>
        </div>
    </article>
</section>
<section>
    <article>
        <FAQ></FAQ>
    </article>
</section>

<Footer />

</template>

<style scoped>
h2{
    color: var(--mainblue);
}

.kontaktContainer{
    display: flex;
    justify-content: space-evenly;
}

a{
    color: var(--mainblue);
}

.kontaktInfo{
    display: flex;
    flex-direction: column;
}

.datoOgTid{
    display: flex;
    justify-content: space-between;
}

img{
    width: 100vw;
    max-height: 50vh;
    object-fit: cover;
}

.socialContainer{
    display: flex;
    flex-direction: column;
}

.socialContainer img{
    width: 100px;
}

@media (max-width: 600px){
    
    .kontaktContainer{
        flex-direction: column;
        margin-left: 8px;
        margin-right: 8px;
    }
    
    h2{
        font-size: 2.5rem;
    }

    .socialContainer img{
    width: 80px;
}
}

</style>