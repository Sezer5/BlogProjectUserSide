<template>
  <div class="headerMainContainer">
    <div class="headerLogoContainer">
      <img :src="Image" alt="Sezer Ünalmış Logo" class="headerLogo">
      <div class="headerLogoName">
        Sezer Ünalmış
      </div>
    </div>
    <div class="headerMenu">
      <RouterLink class="headerMenuItem" to="/">Home</RouterLink>
      <div class="headerMenuItem">About</div>
      <div class="headerMenuItem">Skills</div>
      <div class="headerMenuItem">Work Experience</div>
      <div class="headerMenuItem">Contact</div>
      <div class="headerMenuItem">Blog</div>
    </div>
  </div>
</template>

<script setup>
import Image from '../../images/tekRenkLogom2.png'
</script>

<style>
</style>