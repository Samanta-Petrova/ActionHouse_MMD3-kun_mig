<script setup>
    import navigation from '~/components/navigation.vue';
</script>

<template>
    <Navigation></Navigation>
<section class="omOsContent">
    <img src="../assets/img/omOsHeader.png" alt="billede af medarbejdere fra Action House" loading="lazy">
    <h1>Action House Funcenter i Løkken 
    en Oplevelser for hele familien</h1>
    <p>Action House Funcenter i Løkken tilbyder attraktioner og oplevelser ud over det sædvanlige på hele 12.530 m². Her kan du prøve alt fra Danmarks største indendørs gokartbane til lasergame, bowling, legeland, VR-oplevelser og meget mere - perfekt til familier, venner og firmaevents.</p>
</section>
<tidslinje></tidslinje>
</template>

<style scoped>
template{
    overflow: hidden;
}

.omOsContent{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

h1{
    color: var(--mainblue);
    width: 25ch;
}
img{
    width: 100vw;
    max-height: 50vh;
    object-fit: cover;
}

p{
    width: 70ch;
}

@media (max-width: 400px) {
    template{
        margin-left: 8px;
        margin-right: 8px;
    }

    h1{
        font-size: 2rem;
        width: 15ch;
    }

    p{
        font-size: 0.9rem;
        width: 40ch;
    }
}
</style>