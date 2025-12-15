<script setup>
import BlogBG from '../assets/blog_bg.png'
</script>
<template>
  <h1 class="text-primary font-bold text-6xl text-center">Blog</h1>
  <div class="relative">
    <img class="absolute inset-0 object-cover opacity-30" :src="BlogBG" alt="" />
    <!-- Wrapper with relative positioning for the absolute line -->
    <!-- Single continuous gradient line -->

    <div
      class="grid sm:grid-cols-[auto_1fr] xl:grid-cols-[auto_auto_1fr] gap-x-8 gap-y-10 my-10 text-xl"
    >
      <div class="text-primary">./Choosing a Path</div>
      <div
        class="hidden xl:block left-[calc(auto+16px)] top-2 bottom-20 w-0.5 bg-linear-to-b from-primary to-accent"
      ></div>

      <div class="flex flex-col">
        <h1 class="text-primary text-4xl font-bold">Choosing a Path</h1>
        <p class="text-lettering-dark">12/12/2025</p>
        <p class="text-lettering">
          Led the design and implementation of a custom dashboard application for a major client
          meeting specific requirements for on-prem deployment within an air-gapped and network
          connected environments providing immediate visibility to valuable data and increasing
          revenue for the company following a 3 year contractual agreement due to services rendered
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Inventore, reprehenderit. Sequi,
          quidem atque sit impedit perferendis, voluptatum dolorum molestiae quia fugiat voluptates
          dolores natus est, ut quam repellendus. Maxime autem cum libero officia doloremque vero?
          Quisquam, delectus voluptate! Repellat aperiam accusantium ratione asperiores commodi
          quibusdam dolore hic deleniti eligendi accusamus.
        </p>
      </div>
    </div>
  </div>
</template>
