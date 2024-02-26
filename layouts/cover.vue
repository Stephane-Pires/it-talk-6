<template>
  <div class="slidev-layout intro grid">
    <!-- <LayoutHeader /> -->
    <CornerCurves class="absolute -left-5 -top-5 transform rotate-90" />
     <WindBottom  class="absolute "/>
    
    <div class="flex flex-col justify-center text-center">
      <slot />
    </div>
    <!-- <Zigzags class="absolute top-20 -right-30" /> -->
  </div>
</template>

<style >
.slidev-layout.intro {
  h1 {
    @apply text-6xl leading-20 uppercase;
    font-family: 'Merienda'
  }
  h1 + p {
    @apply -mt-4 text-2xl;
  }
}
</style>