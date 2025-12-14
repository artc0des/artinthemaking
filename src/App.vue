<script setup>
import Splash from './components/Splash.vue'
import About from './views/AboutView.vue'
import Nav from './components/Nav.vue'
import Media from './components/Media.vue'
import Experience from './views/ExperienceView.vue'
import Blog from './views/BlogView.vue'
</script>

<template>
  <div class="container mx-auto">
    <header class="flex justify-between sticky top-0 pt-5 z-50 bg-background">
      <Media></Media>
      <Nav></Nav>
    </header>
    <Splash class="pb-150" msg="Art In The Making" id="home" />
    <section class="mt-150" id="about">
      <About></About>
    </section>
    <section class="mt-50" id="experience">
      <Experience></Experience>
    </section>
    <section class="mt-50 pb-50" id="blog">
      <Blog></Blog>
    </section>
  </div>
</template>
