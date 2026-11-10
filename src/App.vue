<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <header>
      <NavBar />
    </header>

    <main class="flex-grow">
      <HelloWorld />
    </main>

    <Footer />
  </div>
</template>
