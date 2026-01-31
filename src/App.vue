<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #333;
  padding: 1rem;
  z-index: 1000;
}

nav {
  display: flex;
  justify-content: center;
  gap: 2rem;
}

nav a {
  color: white;
  text-decoration: none;
  font-size: 1.2rem;
  font-weight: bold;
}

nav a:hover {
  text-decoration: underline;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>

<style>
/* Global padding to prevent content being hidden behind fixed header */
body {
  margin: 0;
  padding-top: 80px; /* Adjust based on header height */
  font-family: sans-serif;
}
</style>
