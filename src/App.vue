<template>
  <div class="flex min-h-[100vh]">
    <div class="left-sidebar bg-gray-900 flex flex-col">
      <div class="heading p-8 bg-green-900">
        <h1 class="text-2xl text-green-200 text-center">
          Library System
        </h1>
        <div class="text-xl text-gray-300 text-center">
          Finals
        </div>
      </div>
      <center>
        <nav class="nav-links">
          <a class="nav-link" :class="{ 'active': $route.path === '/' }"><RouterLink to="/">User</RouterLink></a>
          <a class="nav-link" :class="{ 'active': $route.path === '/books' }"><RouterLink to="/books">Books</RouterLink></a>
          <a class="nav-link" :class="{ 'active': $route.path === '/borrowedbooks' }"><RouterLink to="/borrowedbooks">Borrowed Books</RouterLink></a>
        </nav>
      </center>
      <div class="p-8 bg-gray-800 text-gray-500 text-center" style="min-height: auto;">
        This library system orchestrates the management, cataloging, and circulation of diverse resources, optimizing accessibility and operational efficiency for patrons and librarians alike.
      </div>
    </div>
    <div class="main-content bg-green-200 flex-1 overflow-y-auto">
      <RouterView />
    </div>
  </div>
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<style scoped>
.left-sidebar {
  position: fixed;
  width: 320px; /* Fixed width */
  height: 100vh;
  overflow-y: auto; /* Enable sidebar scrolling */
}

.main-content {
  margin-left: 320px; /* Adjust content margin to accommodate the sidebar */
  /* Other styles */
}

/* Styles for nav-links, nav-link, etc. */
.nav-links {
  flex: 1;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: stretch;
}

.nav-link {
  padding: 12px;
  background-color: #4a5568;
  color: #cbd5e0;
  text-decoration: none;
  border-bottom: 1px solid #2d3748;
  transition: background-color 0.3s;
}

.nav-link:hover {
  background-color: #2d3748;
}

.active {
  background-color: #2d3748;
}
</style>
