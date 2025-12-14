<script setup>
import { ref, onMounted } from 'vue'
defineProps({
  msg: {
    type: String,
    required: true,
  },
})

const showTitle = ref(false)
const showSubTitle = ref(false)

onMounted(() => {
  setTimeout(() => {
    setTimeout(() => {
      showSubTitle.value = true
    }, 800)

    showTitle.value = true
  }, 1000)
})
</script>

<template>
  <div class="pt-65 transition duration-1000" id="splash">
    <h1
      class="transition duration-1000 text-primary font-bold text-8xl text-center"
      :class="{ 'opacity-0': !showTitle, 'opacity-1000': showTitle }"
    >
      {{ msg }}
    </h1>
    <h3
      class="transition duration-1000 text-white text-center text-2xl mt-10"
      :class="{ 'opacity-0': !showSubTitle, 'opacity-1000': showSubTitle }"
    >
      Product-Focused Engineer <span class="text-accent">|</span> Growth Oriented
      <span class="text-accent">|</span> Full-Stack Systems Thinker
    </h3>
  </div>
</template>
