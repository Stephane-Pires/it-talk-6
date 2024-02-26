<template>
    <div class="slidev-layout punch h-132 w-full flex flex-col justify-center text-center">
            <slot />
    </div>
  </template>
  
  <style>
 .punch {
    @apply bg-brand-light dark:bg-brand-logo;

    h1 {
    @apply text-brand-darker dark:text-dark-text-contrast;
  }
 } 
</style>