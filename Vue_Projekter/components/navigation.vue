<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const menuOpen = ref(false)
const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}
const closeMenu = () => {
  menuOpen.value = false
}

const dropdownOpen = ref(false)
const isMobile = ref(false)

const toggleDropdown = () => {
  dropdownOpen.value = !dropdownOpen.value
}

const closeDropdown = () => {
  dropdownOpen.value = false
}

const handleResize = () => {
  isMobile.value = window.innerWidth <= 400
  if (!isMobile.value) dropdownOpen.value = false
}

const handleOutsideClick = e => {
  if (!isMobile.value) return
  const nav = document.querySelector('.nav')
  if (nav && !nav.contains(e.target)) {
    closeDropdown()
    closeMenu()
  }
}

onMounted(() => {
  handleResize()
  window.addEventListener('resize', handleResize)
  document.addEventListener('click', handleOutsideClick)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
  document.removeEventListener('click', handleOutsideClick)
})
</script>

<template>
  <nav class="nav">
    <div class="nav-logo">
      <NuxtLink to="/">
        <img src="../assets/img/actionhouseLogo.webp" alt="Logo" />
      </NuxtLink>
    </div>

    <button class="burger" @click="toggleMenu" aria-label="Menu" :aria-expanded="menuOpen">
      <span></span>
      <span></span>
      <span></span>
    </button>

    <ul class="nav-links" :class="{ open: menuOpen }">
      <li><NuxtLink to="/aktiviteter" @click="closeMenu">Aktiviteter</NuxtLink></li>
      <li><NuxtLink to="/tilbudspakker" @click="closeMenu">Tilbudspakker</NuxtLink></li>
      <li><NuxtLink to="/booking" @click="closeMenu">Booking</NuxtLink></li>
      <li><NuxtLink to="/spisning" @click="closeMenu">Spisning</NuxtLink></li>
      <li
        class="dropdown"
        @mouseenter="!isMobile && (dropdownOpen = true)"
        @mouseleave="!isMobile && (dropdownOpen = false)"
      >
        <button class="dropdown-toggle" @click="toggleDropdown" :aria-expanded="dropdownOpen">
          Om os <span class="arrow" :class="{ open: dropdownOpen }">▼</span>
        </button>
        <ul class="dropdown-menu" v-if="dropdownOpen">
          <li><NuxtLink to="/omos" @click="() => { closeDropdown(); closeMenu(); }">Om os</NuxtLink></li>
          <li><NuxtLink to="/kontakt" @click="() => { closeDropdown(); closeMenu(); }">Kontakt</NuxtLink></li>
        </ul>
      </li>
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
  color: var(--mainblue);
  font-size: 1.6rem;
  transition: color 0.2s ease;
}

.nav-links a:hover {
  color: var(--mainred);
}

.nav-links a.router-link-active {
  color: var(--mainred);
}

.burger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 2rem;
  height: 1.5rem;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
}

.burger span {
  display: block;
  height: 3px;
  width: 100%;
  background: var(--mainblue);
  border-radius: 2px;
}

.dropdown {
  position: relative;
}

.dropdown-toggle {
  background: none;
  border: none;
  font-size: 1.6rem;
  color: var(--mainblue);
  cursor: pointer;
  font-family: "Fugaz One", sans-serif;
  font-weight: 400;
  display: flex;
  align-items: center;
  gap: 0.3rem;
}

.dropdown-toggle:hover {
  color: var(--mainred);
}

.arrow {
  font-size: 1rem;
  transition: transform 0.2s ease;
}

.arrow.open {
  transform: rotate(180deg);
}

.dropdown-menu {
  position: absolute;
  top: 2.5rem;
  left: 0;
  background: #ffffff;
  list-style: none;
  padding: 0.5rem 1rem;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  z-index: 1000;
}

.dropdown-menu li a {
  font-size: 1.4rem;
  color: var(--mainblue);
}

.dropdown-menu li a:hover {
  color: var(--mainred);
}

@media (max-width: 900px) {
  .nav {
    justify-content: space-between;
  }
  .burger {
    display: flex;
  }
  .nav-links {
    position: fixed;
    top: 5rem;
    left: 0;
    right: 0;
    width: 100%;
    display: none;
    flex-direction: column;
    gap: 1rem;
    padding: 1rem 2rem;
    background: #ffffff;
    box-shadow: 0 8px 24px rgba(0,0,0,0.1);
    z-index: 1000;
  }
  .nav-links.open {
    display: flex;
  }
  .dropdown-menu {
    position: static;
    box-shadow: none;
    padding: 0;
  }
  .dropdown-toggle {
    width: 100%;
    justify-content: space-between;
  }
}
</style>
