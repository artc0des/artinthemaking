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

// Responsive breakpoint detection
const isMobile = ref(window.innerWidth < 768)

const updateScreenSize = () => {
  isMobile.value = window.innerWidth < 768
}

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

  // Listen for window resize to update mobile/desktop view
  window.addEventListener('resize', updateScreenSize)
})

onUnmounted(() => {
  const interactiveElements = document.querySelectorAll('a, button, [role="button"]')

  interactiveElements.forEach((element) => {
    element.removeEventListener('mouseenter', handleMouseEnter)
    element.removeEventListener('mouseleave', handleMouseLeave)
  })

  // Clean up resize listener
  window.removeEventListener('resize', updateScreenSize)
})
</script>

<template>
  <BGAnimationStars v-if="!isMobile" class="bg-animation"></BGAnimationStars>
  <BGAnimationStarsMobile v-else class="bg-animation"></BGAnimationStarsMobile>
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
  /* Hardware acceleration hints */
  will-change: transform;
  transform: translateZ(0);
  backface-visibility: hidden;
  perspective: 1000px;
}
</style>
