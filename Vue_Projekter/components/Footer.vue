<template>
  <footer class="footer">
    <div class="footer-logo">
      <NuxtLink to="/">
        <img src="../assets/img/actionhouseLogo.webp" alt="Logo" />
      </NuxtLink>
    </div>

    <ul class="footer-links">
      <li><NuxtLink to="/">Forside</NuxtLink></li>
      <li><NuxtLink to="/aktiviteter">Aktiviteter</NuxtLink></li>
      <li><NuxtLink to="/spisning">Spisning</NuxtLink></li>
      <li><NuxtLink to="/omos">Om os</NuxtLink></li>
    </ul>

    <div class="footer-info">
      <p>© 2026 Action House Funcenter</p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  padding: 3rem 2rem;
  background-color: #ffffff;
  border-top: 1px solid #e5e5e5;
}

.footer-logo img {
  height: 4rem;
  width: auto;
}

.footer-links {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.footer-links a {
  text-decoration: none;
  color: #0f4980;
  font-weight: 500;
  font-size: 1.4rem;
  transition: color 0.2s ease;
}

.footer-links a:hover {
  color: #cc1824;
}

.footer-links a.router-link-active {
  color: #cc1824;
}

.footer-info p {
  margin: 0;
  font-size: 1.2rem;
  color: #6b6b6b;
  text-align: center;
}
</style>
