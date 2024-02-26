<template>
  <div class="quote-layout  center h-full grid place-content-center">
    <div class="text-center">
      <slot />
    </div>
    <div class="my-auto quote-text">
      <slot name="quote" class="leading-loose"/>
    </div>
    <div class="my-auto quote-author">
      <slot name="author"/>
    </div>
  </div>
</template>

<style >
.quote-layout {
  @apply px-14 py-10 text-[1.1rem] h-full;
    h1 {
    @apply text-4xl mb-8 font-sans font-bold;
  }
}

.quote-text {
    @apply italic hyphens-auto text-center normal-case break-words text-3xl leading-relaxed
}
.quote-author {
    @apply italic bold underline double normal-case text-xl decoration-brand-logo decoration-3 underline-offset-1 capitalize
}

</style>

