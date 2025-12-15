<script setup>
import Splash from './components/Splash.vue'
import About from './views/AboutView.vue'
import Nav from './components/Nav.vue'
import Media from './components/Media.vue'
import Experience from './views/ExperienceView.vue'
import Blog from './views/BlogView.vue'
import { ref } from 'vue'

const mouseX = ref(0)
const mouseY = ref(0)

window.addEventListener('mousemove', (e) => {
  mouseX.value = e.clientX
  mouseY.value = e.clientY
})
</script>

<template>
  <div
    class="pointer rounded-4xl bg-primary border border-primary transition transform transform-3d duration-40"
    :style="{ transform: `translate3d(${mouseX}px, ${mouseY}px, 0) translate(-50%, -50%)` }"
    aria-hidden="true"
  ></div>
  <div class="container mx-auto">
    <header class="flex justify-between sticky top-0 pt-5 z-70 bg-background">
      <Media></Media>
      <Nav></Nav>
    </header>
    <Splash class="pb-150" msg="Art In The Making" id="home" />
    <section class="mt-150" id="about">
      <About></About>
    </section>
    <section class="mt-150" id="experience">
      <Experience></Experience>
    </section>
    <section class="mt-150 pb-50" id="blog">
      <Blog></Blog>
    </section>
  </div>
</template>

<style scoped>
.pointer {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999;
  width: 2rem;
  aspect-ratio: 1;
  pointer-events: none;
}
</style>
