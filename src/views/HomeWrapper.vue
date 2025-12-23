<script setup>
import Splash from '../components/Splash.vue'
import About from './AboutView.vue'
import Experience from './ExperienceView.vue'
</script>
<template>
  <Splash class="pb-150" msg="Art In The Making" id="home" />
  <section class="mt-150" id="about">
    <About></About>
  </section>
  <section class="mt-150" id="experience">
    <Experience></Experience>
  </section>
</template>
