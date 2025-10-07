<template>
  <nav class="navbar">
    <h1 class="logo">Vue Project</h1>
    <div class="links">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/services">Services</router-link>
      <router-link to="/contact">Contact</router-link>
      <DarkMode />
    </div>
  </nav>
</template>

<script setup>
import DarkMode from './DarkMode.vue'
</script>

<style>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: var(--bg-color);
  border-bottom: 1px solid var(--text-color);
}

.logo {
  font-weight: bold;
}

.links {
  display: flex;
  align-items: center;
  gap: 1rem;
}

a {
  color: var(--text-color);
  text-decoration: none;
  font-weight: 500;
}

a.router-link-active {
  text-decoration: underline;
}
</style>
