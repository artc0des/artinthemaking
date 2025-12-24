<script setup>
import BlogBG from '../assets/blog_bg.png'
</script>
<template>
  <section class="pb-150" id="blog">
    <h1 class="text-primary font-bold text-6xl text-center">Blog</h1>
    <div class="relative">
      <img class="absolute inset-0 object-cover opacity-30" :src="BlogBG" alt="" />
      <!-- Wrapper with relative positioning for the absolute line -->
      <!-- Single continuous gradient line -->

      <div
        class="grid sm:grid-cols-[auto_1fr] xl:grid-cols-[auto_auto_1fr] gap-x-8 gap-y-10 my-10 text-xl"
      >
        <div class="text-primary">./Loading...</div>
        <div
          class="hidden xl:block left-[calc(auto+16px)] top-2 bottom-20 w-0.5 bg-linear-to-b from-primary to-accent"
        ></div>

        <div class="flex flex-col">
          <h1 class="text-primary text-4xl font-bold">Future Blog Title Here!</h1>
          <p class="text-lettering-dark">12/12/2025</p>
          <p class="text-lettering">
            I'm playing with the idea of sharing more of my thoughts and challenges through
            blogging. More to come.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
