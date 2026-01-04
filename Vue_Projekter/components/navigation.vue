<template>
    <nav class="nav">
        <div class="nav-logo">
            <NuxtLink to="/">
            <img src="../assets/img/actionhouseLogo.webp" alt="Logo" />
            </NuxtLink>
        </div>

        <ul class="nav-links">
            <li><NuxtLink to="/">Forside</NuxtLink></li>
            <li><NuxtLink to="/aktiviteter">Aktiviteter</NuxtLink></li>
            <li><NuxtLink to="/test">Test</NuxtLink></li>
            <li><NuxtLink to="/spisning">Spisning</NuxtLink></li>
            <li><NuxtLink to="/omos">Om os</NuxtLink></li>
        </ul>
    </nav>
</template>

<style scoped>
.nav {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 3rem;
    padding: 1rem 2rem;
    background-color: #ffffff;
}

.nav-logo img {
    height: 5rem;
    width: auto;
}

.nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
    margin: 0;
    padding: 0;
}

.nav-links a {
    text-decoration: none;
    color: #0f4980;
    font-weight: 500;
    font-size: 1.6rem;
    transition: color 0.2s ease;
    gap: 1rem;
}

.nav-links a:hover {
    color: #cc1824;
}

.nav-links a.router-link-active {
    color: #cc1824;
}

</style>
