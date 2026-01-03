<template>
  <div>
    <header>
      <nav>
        <NuxtLink to="/">Home</NuxtLink> |
        <NuxtLink to="/aktiviteter">Aktiviteter</NuxtLink> |
        <NuxtLink to="/test">Test</NuxtLink>
      </nav>
    </header>

    <main>
      <NuxtPage />
    </main>
 
    <footer>
      <p>&copy; 2025 Projekt Action House</p>
    </footer>
  </div>
</template>
 
<style scoped>
header {
  background-color: #f0f0f0;
  padding: 1rem;
}
nav a {
  margin-right: 1rem;
  text-decoration: none;
  color: #333;
}
main {
  padding: 2rem;
}
footer {
  text-align: center;
  padding: 1rem;
  background-color: #f9f9f9;
  margin-top: 2rem;
}
</style>
