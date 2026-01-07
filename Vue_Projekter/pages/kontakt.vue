<script setup>

</script>

<template>
<section>
    <article>
        <img src="../assets/img/kontaktHeader.png" alt="billeder af mennesker med gokart hjelm">
    </article>
</section>
<section class="kontaktContainer">
    <article class="kontaktInfo">
        <h2>kontakt</h2>
        <p>Telefon +45 99 67</p>
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
    height: 70vh;
}


</style>