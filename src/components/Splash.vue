<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div class="pt-65">
    <h1 class="text-primary font-bold text-8xl text-center">{{ msg }}</h1>
    <h3 class="text-white text-center text-2xl mt-10">
      Product-Focused Engineer <span class="text-accent">|</span> Growth Oriented
      <span class="text-accent">|</span> Full-Stack Systems Thinker
    </h3>
  </div>
</template>
