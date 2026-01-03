<script setup>
    import Header from '../components/navigation.vue'
</script>

<template>
    <Header />
    <div>
    <h1>Aktiviteter.</h1>
    <p>Her finder du alle aktiviteter i Projekt Action House.</p>
  </div>
<NuxtLink to="/">Home</NuxtLink>
<NuxtLink to="/aktiviteter">Aktiviteter</NuxtLink>
<NuxtLink to="/test">Test</NuxtLink>
</template>
 

<style>

    h1{
        color: var(--mainred);
    }
</style>
