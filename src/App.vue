<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Splash from './components/Splash.vue'
import About from './views/AboutView.vue'
import Nav from './components/Nav.vue'
import Media from './components/Media.vue'
import Experience from './views/ExperienceView.vue'
</script>

<template>
  <div class="container mx-auto">
    <header class="flex justify-between sticky top-0 pt-5 z-50 bg-background">
      <Media></Media>
      <Nav></Nav>
    </header>
    <Splash msg="Art In The Making" />
    <section class="mt-150">
      <About></About>
    </section>
    <section class="mt-50">
      <Experience></Experience>
    </section>
  </div>
</template>
