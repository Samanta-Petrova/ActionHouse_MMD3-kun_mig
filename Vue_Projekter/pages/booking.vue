<script>


</script>

<template>

<NuxtLink to="/">Home</NuxtLink>
<NuxtLink to="/aktiviteter">Aktiviteter</NuxtLink>
<NuxtLink to="/test">Test</NuxtLink>
<NuxtLink to="/booking">booking</NuxtLink>

<img src="" alt="">
<h1>Online booking</h1>
<p>Online Booking er KUN en forespørgsel på arrangement. Vi vil sende dig en mail med bekræftelse af din bestilling hurtigst muligt, når den er gået igennem. Er der mindre end 24 timer til du ønsker at besøge os i højsæsoner (skoleferier) anbefaler vi at I ringer og booker i stedet .
<br>
<br>
Vi gør opmærksomme på, at hvis du har Hotmail så kan bekræftelse fremkomme i dine uønsket mail.
<br>
<br>
Det er selvfølgelig også muligt at bestille over telefon på 99 67 67 10.
<br>
<br>
Husk mødetid 20 min før første aktivitet</p>

<div class="bookingContainer">
    <form action="submit" method="post">
        <label for="fName">Fornavn</label>
        <br>
        <input type="text" name="fornavn" id="fName" placeholder="Fornavn">
        <br>
        <label for="eName">Efternavn</label>
        <br>
        <input type="text" name="efternavn" id="eName" placeholder="Efternavn">
        <br>
        <label for="email">E-mail</label>
        <br>
        <input type="email" name="email" id="email" placeholder="actionhouse@actionhouse.dk">
        <br>
        <label for="TelNr">Telefon nr</label>
        <br>
        <input type="tel" name="telefonNr" id="TelNr" placeholder="00009999">
    </form>
</div>
</template>

<style scoped>

h1{
  color: var(--mainblue); 
  text-align: center;
}

p{
    margin-left: 400px;
    margin-right: 400px;
    line-height: 30px;
}

.bookingContainer{
    margin-left: 400px;
    margin-right: 400px;
}


.bookingContainer input{
    width: 1030px;
    height: 35px;
    font-size: 1.2rem;
    margin-bottom: 1rem;
}

.bookingContainer label{
    font-size: 1.5rem;
    font-family: fugaz one;
}



</style>