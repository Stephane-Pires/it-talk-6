<script setup lang="ts">
import { computed } from 'vue'
const props = defineProps<{
  number?: number | string
}>()
</script>

<template>
  <div class="grid grid-cols-2 w-full h-full">
    <WindTop  class="absolute "/>
    <WindMiddle class="absolute" />

    <figure class="w-1/2">
        <div
          class="absolute -left-70 -top-15 rounded-full object-cover h-170 w-170 border border-30 border-number -z-1"
        >
        <span class="flex w-full h-full text-31xl items-center justify-end -ml-20 section-number">
       {{ props.number }}
        </span>
 
        
        </div>

      </figure>
    <div class="slidev-layout center text-center flex flex-col justify-center" :class="props.class">
      <slot />
    </div>
  </div>
</template>

<style scoped>

span {
      font-family: 'Mirenda' !important;
    }
.border-number {
    @apply border-brand-dark dark:border-brand-logo;
}

.section-number {
    @apply text-brand-dark dark:text-brand-logo;
}
</style>
