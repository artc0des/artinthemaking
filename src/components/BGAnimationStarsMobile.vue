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
  <div
    data-us-project="zO0LGlyIKsqrxD7ffb65"
    class="unicorn-embed animation-container"
    data-us-scale="1"
    data-us-dpi="1.5"
    data-us-lazyload="true"
    data-us-alttext="Welcome to Unicorn Studio"
    data-us-arialabel="This is a canvas scene"
  ></div>
</template>

<style scoped>
.animation-container {
  width: 100%;
  height: 100%;
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  /* Hardware acceleration for smooth animations */
  will-change: transform;
  transform: translateZ(0);
  backface-visibility: hidden;
}
</style>
