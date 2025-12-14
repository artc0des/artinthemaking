<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const home = ref('./Home ')
const about = ref(' About Me ')
const experience = ref(' Experience ')
const blog = ref(' Blog ')
const active = ref('home')

const updateMenuItem = (name) => {
  if (name === 'about') {
    about.value = ' ./About Me '
    experience.value = ' Experience '
    home.value = 'Home '
    blog.value = ' Blog '
    active.value = 'about'
  } else if (name === 'experience') {
    about.value = ' About Me '
    home.value = 'Home '
    experience.value = ' ./Experience '
    blog.value = ' Blog '
    active.value = 'experience'
  } else if (name === 'home') {
    about.value = ' About Me '
    home.value = './Home '
    experience.value = ' Experience '
    blog.value = ' Blog '
    active.value = 'home'
  } else {
    about.value = ' About Me '
    experience.value = ' Experience '
    blog.value = ' ./Blog '
    active.value = 'blog'
  }
}

let observer = null

onMounted(() => {
  const sections = document.querySelectorAll('section[id], #home')

  const observerOptions = {
    root: null,
    rootMargin: '-20% 0px -60% 0px',
    threshold: 0
  }

  observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        const sectionId = entry.target.id
        updateMenuItem(sectionId)
      }
    })
  }, observerOptions)

  sections.forEach((section) => {
    observer.observe(section)
  })
})

onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<template>
  <div>
    <p class="text-white text-xl">
      <span class="text-lettering"
        ><a
          href="#home"
          @click="updateMenuItem('home')"
          class="hover:text-primary transition duration-300"
          :class="{ 'text-primary': active === 'home' }"
          >{{ home }}</a
        ></span
      >
      <span class="text-accent">|</span>
      <span class="text-lettering"
        ><a
          href="#about"
          @click="updateMenuItem('about')"
          class="hover:text-primary transition duration-300"
          :class="{ 'text-primary': active === 'about' }"
          >{{ about }}</a
        ></span
      >
      <span class="text-accent">|</span>
      <a
        href="#experience"
        @click="updateMenuItem('experience')"
        class="hover:text-primary transition duration-300"
        :class="{ 'text-primary': active === 'experience' }"
      >
        {{ experience }}
      </a>
      <span class="text-accent">|</span>
      <a
        href="#blog"
        @click="updateMenuItem('blog')"
        class="hover:text-primary transition duration-300"
        :class="{ 'text-primary': active === 'blog' }"
      >
        {{ blog }}</a
      >
    </p>
  </div>
</template>
