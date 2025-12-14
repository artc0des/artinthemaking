<template>
  <h1 class="text-primary font-bold text-6xl text-center">Blog</h1>

  <!-- Wrapper with relative positioning for the absolute line -->
  <div class="relative">
    <!-- Single continuous gradient line -->
    <div
      class="hidden xl:block absolute ml-[20%] left-[calc(auto+16px)] top-2 bottom-20 w-0.5 bg-linear-to-b from-primary to-accent"
    ></div>

    <div
      class="grid sm:grid-cols-[auto_1fr] xl:grid-cols-[auto_1fr] gap-x-8 gap-y-10 my-10 text-xl"
    >
      <div class="text-primary">./Consistency & Self-Doubt</div>

      <div class="flex flex-col">
        <h1 class="text-primary text-4xl font-bold">Consistency & Self-Doubt</h1>
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
