<script setup>
import BlueSky from '../components/icons/IconBlueSky.vue'
import LinkedIn from '../components/icons/IconLinkedIn.vue'
import Github from '../components/icons/IconGithub.vue'
import Email from '../components/icons/IconEmail.vue'
import Youtube from '../components/icons/IconYoutube.vue'
import Headroom from '../components/icons/IconHeadroom.vue'
</script>

<template>
  <div class="flex items-center gap-1 md:gap-2">
    <Headroom class="w-5 h-5 md:w-6 md:h-6"></Headroom>
    <span class="text-accent select-none" aria-hidden="true">|</span>
    <LinkedIn class="w-5 h-5 md:w-6 md:h-6"></LinkedIn>
    <Github class="w-5 h-5 md:w-6 md:h-6"></Github>
    <BlueSky class="w-5 h-5 md:w-6 md:h-6"></BlueSky>
    <Email class="w-5 h-5 md:w-6 md:h-6"></Email>
    <Youtube class="w-5 h-5 md:w-6 md:h-6"></Youtube>
  </div>
</template>
