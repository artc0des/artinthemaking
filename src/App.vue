<script setup>
import Nav from './components/Nav.vue'
import Media from './components/Media.vue'
import Footer from './components/Footer.vue'
import BGAnimationStars from './components/BGAnimationStars.vue'
import { ref, onMounted, onUnmounted } from 'vue'
import BGAnimationStarsMobile from './components/BGAnimationStarsMobile.vue'

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
  <BGAnimationStars class="bg-animation hidden md:block"></BGAnimationStars>
  <BGAnimationStarsMobile class="bg-animation md:hidden"></BGAnimationStarsMobile>
  <div class="container mx-auto px-4 md:px-6">
    <header class="flex justify-between items-center sticky top-0 py-4 md:pt-5 z-70 bg-transparent">
      <Media></Media>
      <Nav></Nav>
    </header>
    <RouterView></RouterView>
    <Footer></Footer>
  </div>
</template>

<style scoped>
.bg-animation {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  pointer-events: none;
  overflow: hidden;
}
</style>
