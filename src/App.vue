<script setup>
import Nav from './components/Nav.vue'
import Media from './components/Media.vue'
import Footer from './components/Footer.vue'
import { ref, onMounted, onUnmounted } from 'vue'

const mouseX = ref(0)
const mouseY = ref(0)
const isReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches
const isTouch = window.matchMedia('(pointer: coarse)').matches
const shouldRun = !isReducedMotion && !isTouch
const isHoveringLink = ref(false)

if (shouldRun) {
  window.addEventListener('mousemove', (e) => {
    mouseX.value = e.clientX
    mouseY.value = e.clientY
  })
}

const handleMouseEnter = () => {
  isHoveringLink.value = true
}

const handleMouseLeave = () => {
  isHoveringLink.value = false
}

onMounted(() => {
  // Select all interactive elements (links, buttons, etc.)
  const interactiveElements = document.querySelectorAll('a, button, [role="button"]')

  interactiveElements.forEach((element) => {
    element.addEventListener('mouseenter', handleMouseEnter)
    element.addEventListener('mouseleave', handleMouseLeave)
  })
})

onUnmounted(() => {
  const interactiveElements = document.querySelectorAll('a, button, [role="button"]')

  interactiveElements.forEach((element) => {
    element.removeEventListener('mouseenter', handleMouseEnter)
    element.removeEventListener('mouseleave', handleMouseLeave)
  })
})
</script>

<template>
  <div
    class="pointer rounded-4xl bg-transparent border border-primary transition transform transform-3d duration-40"
    :style="{ transform: `translate3d(${mouseX}px, ${mouseY}px, 0) translate(-50%, -50%)` }"
    aria-hidden="true"
  ></div>
  <div
    class="center rounded-4xl bg-accent border border-background transition transform transform-3d duration-100"
    :class="{ 'center-expanded': isHoveringLink }"
    :style="{ transform: `translate3d(${mouseX}px, ${mouseY}px, 0) translate(-50%, -50%)` }"
    aria-hidden="true"
  ></div>
  <div class="container mx-auto px-4 md:px-6">
    <header class="flex justify-between items-center sticky top-0 py-4 md:pt-5 z-70 bg-background">
      <Media></Media>
      <Nav></Nav>
    </header>
    <RouterView></RouterView>
    <Footer></Footer>
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
.center {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999;
  width: 1rem;
  aspect-ratio: 1;
  pointer-events: none;
  transition:
    width 0.3s ease,
    background-color 0.3s ease;
}

.center-expanded {
  width: 5rem;
  background-color: transparent;
}
</style>
