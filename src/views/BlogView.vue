<script setup>
import BGAnimationBlog from '@/components/BGAnimationBlog.vue'
import BlogBG from '../assets/blog_bg.png'
</script>
<template>
  <section class="pb-150" id="blog">
    <h1 class="text-primary font-bold text-6xl text-center">Blog</h1>
    <div class="relative min-h-screen">
      <BGAnimationBlog
        class="hidden md:block md:w-fit md:h-fit md:absolute md:top-0 md:left-1/2 md:-translate-x-1/2 transition duration-1000 opacity-70 pointer-events-none"
      ></BGAnimationBlog>
      <div class="relative z-50 flex justify-center">
        <div>
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
      </div>
    </div>
  </section>
</template>
