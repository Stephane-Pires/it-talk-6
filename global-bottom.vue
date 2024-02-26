<script setup lang="ts">
import { computed } from 'vue'
import { useNow } from '@vueuse/core'

const now  = useNow()
const options = { weekday: 'short', year: 'numeric', month: 'long', day: 'numeric' };
const date = computed(() => now?.value.toLocaleDateString($slidev.configs.dateFormat, options))

</script>

<template>
  <footer
    class="absolute z-40 bottom-0 p-2 text-sm w-full h-6"
  >
      <div 
    class="absolute bottom-0">

        {{ $slidev.configs.presenterName }}
      
      </div>
      <div 
       class="absolute bottom-0 left-100"> {{date}}</div>
      <div
        class="text-xs absolute bottom-0 right-2"
      >
        <SlideCurrentNo /> / <SlidesTotal />
      </div>
  </footer>
</template>

<style scoped>

  footer {
  @apply font-mono  text-brand-darker dark:text-brand-light bg-brand-light dark:bg-light-text-base;
  }

</style>