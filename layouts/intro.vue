<template>
  <div class="slidev-layout ">
    <CornerCurves class="absolute -right-30 -top-5 transform rotate-180" />
    <CornerCurves class="absolute left-0 top-0 transform rotate-90" />
    <div class="flex items-center mt-15">
      <figure class="w-1/2">
        <img
          :src="$attrs.presenterImage"
          class="relative rounded-full object-cover h-80 w-80 border border-8 border-secondary-400 z-10"
        />
      </figure>
      <div class="w-1/2">
        <slot />
      </div>
    </div>
  </div>
</template>