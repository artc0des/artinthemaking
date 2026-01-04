<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  // Load the UnicornStudio library if not already loaded
  if (!window.UnicornStudio) {
    window.UnicornStudio = { isInitialized: !1 }
    var script = document.createElement('script')
    script.src =
      'https://cdn.jsdelivr.net/gh/hiunicornstudio/unicornstudio.js@v2.0.0/dist/unicornStudio.umd.js'
    script.onload = function () {
      // Initialize UnicornStudio after the script loads
      if (window.UnicornStudio && typeof window.UnicornStudio.init === 'function') {
        window.UnicornStudio.init()
        window.UnicornStudio.isInitialized = true
      }
    }
    ;(document.head || document.body).appendChild(script)
  } else {
    // Library already loaded, just call init() for this component instance
    if (typeof window.UnicornStudio.init === 'function') {
      window.UnicornStudio.init()
    }
  }
})
</script>

<template>
  <div data-us-project="cLtdOPPcDJeGz6arvCjk" style="width: 1440px; height: 900px"></div>
</template>

<style scoped>
.unicorn-container {
  /* Ensure it fills the desired area */
  display: block;
  position: relative;
  overflow: hidden;
}
</style>
