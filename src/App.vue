<script setup>
import HeaderPage from "./components/HeaderPage.vue";
import MainKasper from "./components/MainKasper.vue";
import FooterPage from "./components/FooterPage.vue";
</script>

<template>
  <header>
    <HeaderPage />
  </header>

  <main>
    <MainKasper />
  </main>

  <footer>
    <FooterPage />
  </footer>
</template>

<style>
@import "./assets/main.css";
div#app {
  overflow-x: hidden;
}
</style>
