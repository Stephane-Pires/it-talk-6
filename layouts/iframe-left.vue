<script setup lang="ts">
const props = defineProps<{ class?: string; url: string }>()
</script>

<template>
  <div class="grid grid-cols-2 w-full h-full">
    <CornerCurves class="absolute right-0 top-0 transform rotate-180 scale-30" />
    <CornerCurves class="absolute left-1/2 bottom-0 transform rotate-0 scale-30" />
    <div class="h-full">
      <iframe id="frame" class="w-full h-full" :src="url" />
    </div>
    <div class="slidev-layout default flex flex-col justify-evenly" :class="props.class">
      <slot />
    </div>
  </div>
</template>