<script>
import bookingForm from '~/components/bookingForm.vue';
</script>

<template>
<div>
    <NuxtLink to="/">Home</NuxtLink>
    <NuxtLink to="/aktiviteter">Aktiviteter</NuxtLink>
    <NuxtLink to="/test">Test</NuxtLink>
    <NuxtLink to="/booking">booking</NuxtLink>
</div>

<img src="../assets/img/bookingHeader.jpg" alt="billede af en der bowler">
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
<BookingForm></BookingForm>
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

img{
    margin: 0 auto;
    width: 1400px;
    height: 600px;
    object-fit: cover;
}





</style>