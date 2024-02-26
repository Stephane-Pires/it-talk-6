<script setup lang="ts">
import { computed } from 'vue'
import { handleBackground } from '../layout-helpers'
const props = defineProps({
  image: {
    type: String,
  },
  class: {
    type: String,
  },
})
const style = computed(() => handleBackground(props.image))
</script>

<template>
  <div class="grid grid-cols-2 w-full h-full">
       <CornerCurves class="absolute left-0 top-0 transform rotate-90 scale-30" />
      <CornerCurves class="absolute left-1/2 bottom-0 transform -rotate-90 scale-30" />
    <div class="slidev-layout default flex flex-col justify-evenly" :class="props.class">
      <slot />
    </div>
    <div class="w-full w-full" :style="style" />
  </div>
</template>