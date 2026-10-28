<script setup>
import { ref, onMounted } from 'vue'
import BGAnimation from './BGAnimation.vue'
import headroomLogo from '../assets/headroom.svg'
defineProps({
  msg: {
    type: String,
    required: true,
  },
})

const showTitle = ref(false)
const showSubTitle = ref(false)
const showBG = ref(false)
const bgKey = ref(0)

const startAnimation = () => {
  // Reset all states first
  showTitle.value = false
  showSubTitle.value = false
  showBG.value = false

  // Start the animation sequence
  setTimeout(() => {
    setTimeout(() => {
      setTimeout(() => {
        showBG.value = true
      }, 800)
      showSubTitle.value = true
    }, 1000)
    showTitle.value = true
  }, 1200)
}

onMounted(() => {
  // Force BGAnimation to remount by changing its key
  bgKey.value = Math.random()
  startAnimation()
})
</script>

<template>
  <div v-bind="$attrs">
    <div class="relative min-h-screen">
      <BGAnimation
        :key="bgKey"
        class="hidden md:block md:w-fit md:h-fit md:absolute md:top-0 md:left-1/2 md:-translate-x-1/2 transition duration-1000 pointer-events-none"
        :class="{ 'opacity-0': !showBG, 'opacity-100': showBG }"
      ></BGAnimation>
      <div
        class="relative flex justify-center items-start pt-65 xl:pt-75 transition duration-1000 z-50"
        id="splash"
      >
        <div>
          <h1
            class="transition duration-1000 text-primary font-bold text-4xl xl:text-8xl text-center"
            :class="{ 'opacity-0': !showTitle, 'opacity-100': showTitle }"
          >
            {{ msg }}
          </h1>
          <h3
            class="transition duration-1000 text-white text-center text-2xl mt-5"
            :class="{ 'opacity-0': !showSubTitle, 'opacity-100': showSubTitle }"
          >
            Product-Focused Engineer <span class="text-accent">|</span> Growth Oriented
            <span class="text-accent">|</span> Full-Stack Systems Thinker
          </h3>
          <div
            class="flex justify-center mt-10 transition-opacity duration-1000"
            :class="{ 'opacity-0': !showSubTitle, 'opacity-100': showSubTitle }"
          >
            <a
              href="https://whatsmyheadroom.com/?utm_source=artinthemaking.me&utm_medium=referral&utm_campaign=home_splash"
              target="_blank"
              rel="noopener"
              class="group flex items-center gap-3 rounded-full border border-accent/60 bg-background/70 px-4 py-2 text-lettering transition duration-300 hover:border-primary hover:text-white"
            >
              <img :src="headroomLogo" alt="" class="h-9 w-9 md:h-10 md:w-10 object-contain" />
              <span class="text-sm md:text-base text-left">
                <span class="text-primary font-semibold">Now building: Headroom</span>
                <span class="text-accent hidden md:inline"> | </span>
                <span class="block md:inline">
                  What's free to spend before payday
                  <span
                    class="inline-block text-primary transition duration-300 group-hover:translate-x-1"
                    >→</span
                  >
                </span>
              </span>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
