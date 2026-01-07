<script setup>
import navigation from '~/components/navigation.vue';
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
        <h2>kontakt</h2>
        <p>Telefon +45 99 67 67 10</p>
        <p>email: info@actionhouse.dk</p>
        <h2>Følg os på:</h2>
    </article>
    <article class="kontaktDato">
        <h2>åbningstider</h2>
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
</template>

<style scoped>
h2{
    color: var(--mainblue);
}

.kontaktContainer{
    display: flex;
    justify-content: space-evenly;
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

@media (max-width: 400px){
    
    .kontaktContainer{
        flex-direction: column;
        margin-left: 8px;
        margin-right: 8px;
    }
    
    h2{
        font-size: 2.5rem;
    }


}

</style>