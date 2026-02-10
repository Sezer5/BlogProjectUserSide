<template>
  <div>
    <Header />
    <Banner />
    <Home />
    <Footer />
  </div>
</template>

<script setup>
import Home from "./components/Home.vue";
import Header from "./components/layouts/Header.vue";
import Footer from "./components/layouts/Footer.vue";
import Banner from "./components/layouts/Banner.vue"
import { RouterLink, RouterView } from "vue-router";
</script>

<style>
</style>