<template>
  <div>
    <Header />
    <Home />
    <Footer />
  </div>
</template>

<script setup>
import Home from "./components/Home.vue";
import Header from "./components/layouts/Header.vue";
import Footer from "./components/layouts/Footer.vue";
import { RouterLink, RouterView } from "vue-router";
</script>

<style>
</style>