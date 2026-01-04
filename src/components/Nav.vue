<script setup>
import { ref, onMounted, onUnmounted, nextTick, watch } from 'vue'
import { useRouter, useRoute } from 'vue-router'

const router = useRouter()
const route = useRoute()

const home = ref('./Home ')
const about = ref(' About Me ')
const experience = ref(' Experience ')
const blog = ref(' Blog ')
const active = ref('home')
const isMobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

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
    home.value = 'Home '
    experience.value = ' Experience '
    blog.value = ' ./Blog '
    active.value = 'blog'
  }
}

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}

const handleNavClick = (sectionId, event) => {
  event.preventDefault()
  updateMenuItem(sectionId)
  closeMobileMenu()

  if (route.path === '/') {
    scrollToSection(sectionId)
  } else {
    router.push({ path: '/', hash: `#${sectionId}` })
  }
}

let observer = null

const setupObserver = () => {
  // Disconnect existing observer if any
  if (observer) {
    observer.disconnect()
  }

  // Only set up observer on home page
  if (route.path !== '/') {
    return
  }

  // Use a longer delay to ensure RouterView content is fully rendered
  setTimeout(() => {
    const sections = document.querySelectorAll('section[id], #home')

    // If no sections found, retry after a short delay
    if (sections.length === 0) {
      setTimeout(setupObserver, 100)
      return
    }

    const observerOptions = {
      root: null,
      rootMargin: '-20% 0px -60% 0px',
      threshold: 0,
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
  }, 300)
}

onMounted(() => {
  setupObserver()
})

// Watch for route changes and reinitialize observer
watch(
  () => route.path,
  () => {
    setupObserver()
  },
)

onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<template>
  <div>
    <!-- Desktop Navigation -->
    <nav class="hidden md:block">
      <p class="text-white text-xl">
        <span class="text-lettering">
          <a
            href="#home"
            @click="handleNavClick('home', $event)"
            class="hover:text-primary transition duration-300"
            :class="{ 'text-primary': active === 'home' }"
          >
            {{ home }}
          </a>
        </span>
        <span class="text-accent">|</span>
        <span class="text-lettering">
          <a
            href="#about"
            @click="handleNavClick('about', $event)"
            class="hover:text-primary transition duration-300"
            :class="{ 'text-primary': active === 'about' }"
          >
            {{ about }}
          </a>
        </span>
        <span class="text-accent">|</span>
        <span class="text-lettering">
          <a
            href="#experience"
            @click="handleNavClick('experience', $event)"
            class="hover:text-primary transition duration-300"
            :class="{ 'text-primary': active === 'experience' }"
          >
            {{ experience }}
          </a>
        </span>
        <span class="text-accent">|</span>
        <span class="text-lettering">
          <RouterLink
            to="/blog"
            @click="updateMenuItem('blog')"
            class="hover:text-primary transition duration-300"
            :class="{ 'text-primary': active === 'blog' }"
          >
            {{ blog }}
          </RouterLink>
        </span>
      </p>
    </nav>

    <!-- Mobile Hamburger Button -->
    <button
      @click="toggleMobileMenu"
      class="md:hidden text-lettering hover:text-primary transition duration-300 p-2"
      aria-label="Toggle menu"
    >
      <svg
        class="w-6 h-6"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          v-if="!isMobileMenuOpen"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16M4 18h16"
        ></path>
        <path
          v-else
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        ></path>
      </svg>
    </button>

    <!-- Mobile Menu Overlay -->
    <Transition name="fade">
      <div
        v-if="isMobileMenuOpen"
        @click="closeMobileMenu"
        class="fixed inset-0 bg-opacity-50 z-40 md:hidden"
      ></div>
    </Transition>

    <!-- Mobile Menu Slide-out -->
    <Transition name="slide">
      <nav
        v-if="isMobileMenuOpen"
        class="fixed top-0 right-0 h-full w-64 bg-background border-l border-accent z-50 md:hidden"
      >
        <div class="flex flex-col p-6 space-y-6">
          <button
            @click="closeMobileMenu"
            class="self-end text-lettering hover:text-primary transition duration-300"
            aria-label="Close menu"
          >
            <svg
              class="w-6 h-6"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              ></path>
            </svg>
          </button>

          <a
            href="#home"
            @click="handleNavClick('home', $event)"
            class="text-lettering text-xl hover:text-primary transition duration-300 py-2"
            :class="{ 'text-primary': active === 'home' }"
          >
            {{ home }}
          </a>

          <a
            href="#about"
            @click="handleNavClick('about', $event)"
            class="text-lettering text-xl hover:text-primary transition duration-300 py-2"
            :class="{ 'text-primary': active === 'about' }"
          >
            {{ about }}
          </a>

          <a
            href="#experience"
            @click="handleNavClick('experience', $event)"
            class="text-lettering text-xl hover:text-primary transition duration-300 py-2"
            :class="{ 'text-primary': active === 'experience' }"
          >
            {{ experience }}
          </a>

          <RouterLink
            to="/blog"
            @click="(updateMenuItem('blog'), closeMobileMenu())"
            class="text-lettering text-xl hover:text-primary transition duration-300 py-2"
            :class="{ 'text-primary': active === 'blog' }"
          >
            {{ blog }}
          </RouterLink>
        </div>
      </nav>
    </Transition>
  </div>
</template>

<style scoped>
/* Fade transition for overlay */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Slide transition for mobile menu */
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.3s ease;
}

.slide-enter-from,
.slide-leave-to {
  transform: translateX(100%);
}
</style>
