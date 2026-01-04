<script setup>
import BGAnimationAbout from '@/components/BGAnimationAbout.vue'
</script>
<template>
  <div class="relative min-h-screen">
    <BGAnimationAbout
      class="hidden md:block md:w-fit md:h-fit md:absolute md:left-1/2 md:-translate-x-1/2 transition duration-1000 opacity-70 pointer-events-none"
    ></BGAnimationAbout>

    <div class="relative z-50 flex justify-center items-start pt-10 xl:pt-20">
      <div class="max-w-4xl px-4">
        <h1 class="text-primary font-bold text-6xl text-center">About Me</h1>
        <p class="text-lettering md:text-xl mt-10">
          I’m a product-focused creator who thrives on the combination of creativity and
          organization required to bring a vision to life. I still find joy in losing track of time
          while turning complex ideas into clean, accessible solutions.<br /><br />

          Technically, I bring 9 years of experience in full-stack development, currently diving
          deep into <span class="font-bold">Go </span>and <span class="font-bold">Vue.js</span>. My
          background spans finance and real-time data monitoring, where I’ve learned that strong
          system design means nothing without genuine empathy for the user. I don't just write code;
          I think about the complete lifecycle—organizing systems with clarity and accessibility in
          mind. I see technology as a tool to serve people, not an end in itself.<br /><br />

          Beyond the screen, I’m dedicated to designing a life that aligns with my values of growth
          and intentional creation. I’m a big believer in transformation—whether that’s refactoring
          a codebase, producing music (a passion that evolved from dance to DJing), or simply
          sitting in a coffee shop journaling to build my relationship with patience and
          presence.<br /><br />

          I am working toward a future where I can create meaningful impact while maintaining
          autonomy. If you are building something that helps people transform, or if you value
          thoughtful, user-centered creation, let's connect.
        </p>
      </div>
    </div>
  </div>
</template>
