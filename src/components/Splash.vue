<script setup>
import { ref, onMounted } from 'vue'
import BgImage from '../assets/bg_image.png'
defineProps({
  msg: {
    type: String,
    required: true,
  },
})

const showTitle = ref(false)
const showSubTitle = ref(false)
const showBG = ref(false)

onMounted(() => {
  setTimeout(() => {
    setTimeout(() => {
      setTimeout(() => {
        showBG.value = true
      }, 800)
      showSubTitle.value = true
    }, 1000)
    showTitle.value = true
  }, 1200)
})
</script>

<template>
  <div>
    <img
      class="w-fit h-fit xl:w-full xl:h-full relative transition duration-1000"
      :class="{ 'opacity-0': !showBG, 'opacity-30': showBG }"
      :src="BgImage"
      alt=""
    />
    <div
      class="absolute top-0 xl:top-10 xl:left-70 pt-65 transition duration-1000 z-50"
      id="splash"
    >
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
    </div>
  </div>
</template>
