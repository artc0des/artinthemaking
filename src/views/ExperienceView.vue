<script setup>
import ExperienceBG from '../assets/experience_bg.png'
</script>
<template>
  <h1 class="text-primary font-bold text-6xl text-center">Experience</h1>
  <div class="xl:relative">
    <img
      class="hidden xl:block absolute inset-0 top-50 object-cover opacity-15"
      :src="ExperienceBG"
      alt=""
    />
    <div class="px-5 py-2 border-2 border-accent rounded-2xl mt-5">
      <div class="grid sm:grid-cols-1 xl:grid-cols-3 gap-x-4 gap-y-10 my-10 text-xl">
        <div class="flex flex-col">
          <p class="text-lettering font-bold">Frontend & UI/UX</p>
          <p class="text-lettering-dark">Vue 3, TailwindCSS 4, Vite</p>
          <p class="text-lettering">
            Passionate about crafting responsive, high-performance interfaces. I specialize in
            modern UI/UX implementation, utilizing the speed of Vite and the flexibility of Tailwind
            CSS 4 to build intuitive user experiences.
          </p>
        </div>

        <div class="flex flex-col">
          <p class="text-lettering font-bold">Backend Engineering</p>
          <p class="text-lettering-dark">Go (Golang), Java, System Design</p>
          <p class="text-lettering">
            Experienced in architecting robust, scalable server-side solutions. My focus is on
            efficient backend system design and implementation using Go, ensuring reliability in
            complex, data-driven environments.
          </p>
        </div>

        <div class="flex flex-col">
          <p class="text-lettering font-bold">Full Stack Development</p>
          <p class="text-lettering-dark">End-to-End, Architecture, Docker</p>
          <p class="text-lettering">
            Bridging the gap between design and functionality. I provide complete design and
            implementation capabilities, managing the entire lifecycle from database structure to
            the final pixel on the screen.
          </p>
        </div>
      </div>
    </div>
    <!-- Wrapper with relative positioning for the absolute line -->
    <div class="relative">
      <!-- Single continuous gradient line -->
      <div
        class="hidden xl:block absolute ml-39 left-[calc(auto+16px)] top-2 bottom-20 w-0.5 bg-linear-to-b from-primary to-accent"
      ></div>
      <div
        class="grid sm:grid-cols-[auto_1fr] xl:grid-cols-[auto_auto_1fr] gap-x-4 gap-y-10 my-10 text-xl"
      >
        <!--HP Inc. Experence-->
        <div class="text-lettering-dark">2025 - Present</div>

        <div class="relative hidden xl:flex justify-center">
          <div
            class="w-6 h-6 mt-2 rounded-full bg-primary border-2 border-background shadow-lg shadow-primary/50 z-10"
          ></div>
        </div>

        <div class="flex flex-col">
          <h1 class="text-primary text-4xl font-bold">HP Inc.</h1>
          <p class="text-lettering font-bold">Senior Software Engineer</p>
          <p class="text-lettering">
            Led the design and implementation of a custom dashboard application for a major client
            meeting specific requirements for on-prem deployment within an air-gapped and network
            connected environments providing immediate visibility to valuable data and increasing
            revenue for the company following a 3 year contractual agreement due to services
            rendered
          </p>
          <div class="flex mt-5">
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Vue.js</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Go</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Docker</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Linux</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Java 17</span
            >
          </div>
        </div>
        <!--Schwab Experence-->
        <div class="text-lettering-dark">2022 - 2025</div>

        <div class="relative hidden xl:flex justify-center">
          <div
            class="w-6 h-6 mt-2 rounded-full bg-primary border-2 border-background shadow-lg shadow-primary z-10"
          ></div>
        </div>

        <div class="flex flex-col">
          <h1 class="text-primary text-4xl font-bold">Charles Schwab</h1>
          <p class="text-lettering font-bold">Senior Software Engineer</p>
          <p class="text-lettering">
            Led the design and implementation an improved user navigation system, displaying
            accurate navigation data and product recommendations in a SPA and MPA system, expanding
            coverage to 99% from 70% across all of Schwab.com while removing external team
            dependencies
          </p>
          <div class="flex mt-5">
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >C#</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >ASP.NET</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >PCF</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >React</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Typescript</span
            >
          </div>
        </div>
        <!--Schwab Cont-->
        <div class="text-lettering-dark">2016 - 2022</div>

        <div class="relative hidden xl:flex justify-center">
          <div
            class="w-6 h-6 mt-2 rounded-full bg-primary border-2 border-background shadow-lg shadow-primary z-10"
          ></div>
        </div>

        <div class="flex flex-col">
          <p class="text-lettering font-bold">Associate Software Engineer</p>
          <p class="text-lettering">
            Led the redesign of a critical client data store system, replacing a legacy
            spreadsheet-based model with a Java-backed MySQL persistence layer, mitigating potential
            millions in risk of data loss and improving data accessibility for downstream systems
          </p>
          <div class="flex mt-5">
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >SprintBoot</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Java 8</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >PostgreSQL</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Splunk</span
            >
          </div>
        </div>
        <!--Mindtree LTD-->
        <div class="text-lettering-dark">2015-2016</div>

        <div class="relative hidden xl:flex justify-center">
          <div
            class="w-6 h-6 mt-2 rounded-full bg-primary border-2 border-background shadow-lg shadow-primary z-10"
          ></div>
        </div>

        <div class="flex flex-col">
          <h1 class="text-primary text-4xl font-bold">Mindtree LTD.</h1>
          <p class="text-lettering font-bold">Software Engineer</p>
          <p class="text-lettering">
            Developed an internal deployment tracking tool that improved cross-team productivity,
            resulting in a 10% reduction in deployment-related errors
          </p>
          <div class="flex mt-5">
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Java 8</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Jenkins</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >Bamboo</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >DevOps</span
            >
          </div>
        </div>
        <!--Mindtree Cont-->
        <div class="text-lettering-dark">2014-2015</div>

        <div class="relative hidden xl:flex justify-center">
          <div
            class="w-6 h-6 mt-2 rounded-full bg-primary border-2 border-background shadow-lg shadow-primary z-10"
          ></div>
        </div>

        <div class="flex flex-col">
          <p class="text-lettering font-bold">Software Engineer Intern</p>
          <p class="text-lettering">
            Successfully integrated shell scripts in AWS cloud servers, resulting in the automation
            of DevOps processes and the reduction of risk during deployment by removing manual steps
          </p>
          <div class="flex mt-5">
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >C#</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >ASP.NET</span
            >
            <span
              class="mr-5 border rounded-4xl border-primary bg-button-bg text-primary text-xl px-2"
              >AWS</span
            >
          </div>
        </div>
      </div>
    </div>
    <div class="flex justify-center">
      <button class="border rounded-4xl text-primary text-2xl px-2 max-w-fit">
        View Full Resume
      </button>
    </div>
  </div>
</template>
