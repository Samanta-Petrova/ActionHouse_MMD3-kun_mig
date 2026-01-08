<script>
import bookingForm from '~/components/bookingForm.vue';
import navigation from '~/components/navigation.vue';
import Footer from '../components/Footer.vue'
</script>

<template>
<Navigation></Navigation>
<section>
    <article class="bookingIntro">
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
    </article>
</section>

<div class="bookingContainer">
<BookingForm></BookingForm>
</div>

<Footer />

</template>

<style scoped>
template{
    margin-left: 8.65625rem;
    margin-right: 8.65625rem;
}

.bookingIntro{
    display: flex;
    flex-direction: column;
    align-items: center;
}

.bookingIntro h1{
  color: var(--mainblue); 

}

.bookingIntro p{
    line-height: 30px;
    max-width: 70ch;
}

.bookingIntro img{
    width: 100%;
    max-height: 50vh;
    object-fit: cover;
}

@media (max-width: 600px) {
    template{
        max-width: 400px;
    }
   
    p{
        width: 40ch;
        font-size: 0.9rem;
    }

    h1{
        font-size: 2rem;
    }
}




</style>