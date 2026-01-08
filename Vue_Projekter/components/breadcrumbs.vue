<template>
  <nav class="breadcrumb">
    <NuxtLink to="/">Forside</NuxtLink>
    <span class="sep" v-if="isAktiviteter">/</span>
    <NuxtLink v-if="isAktiviteter" to="/aktiviteter">Aktiviteter</NuxtLink>
    <span class="sep" v-if="label">/</span>
    <span v-if="label" class="crumb">{{ label }}</span>
  </nav>
</template>

<script setup>
import { useRoute } from 'vue-router'

const route = useRoute()

// Map slugs til pæne labels, da det eller står med småt
const names = {
  bowling: 'Bowling',
  gokart: 'Gokart',
  lasergame: 'Lasergame',
  legeland: 'Legeland'
}

const pathParts = route.path.split('/').filter(Boolean)
const isAktiviteter = route.path.startsWith('/aktiviteter')

// Sidste del af stien
const last = pathParts[pathParts.length - 1]

// Brug mapping, fallback til capitalized slug
const label = names[last] ?? (last ? last.charAt(0).toUpperCase() + last.slice(1) : '')
</script>

<style>
.breadcrumb {
  font-family: var(--font-family, inherit);
  font-size: 0.95rem;
  color: #154B82;
  display: flex;
  align-items: center;
  gap: 0.35rem;
  margin: 1rem 0;
}

.breadcrumb a {
  color: #154B82;
  text-decoration: underline;
  font-weight: 500;
}

.breadcrumb a:hover {
  color: #cc1824;
}

.breadcrumb .crumb {
  color: #154B82;
  font-weight: 500;        
  text-decoration: none;   
}

.breadcrumb .sep {
  opacity: 0.6;
}
</style>
