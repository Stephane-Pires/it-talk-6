<script setup lang="ts">
const props = defineProps(
    {
        type: 'accent' | 'info' | 'warning',
        title: String,
    }
        )
</script>


<template>
    <div class="my-auto" :class="props.type">
     <h1>
        {{ props.title }}
     </h1>
      <slot />
    </div>
</template>

<style scoped>
  .accent {
  @apply border-dark-accent border-5 bg-light-accent p-6 bg-opacity-15 border-opacity-15;

  h1 {
    @apply text-2xl text-dark-accent dark:text-light-accent mb-4
  }
  }

    .warning {
  @apply border-dark-warning border-5 bg-light-warning p-6 bg-opacity-15 border-opacity-15;
  
  h1 {
    @apply text-2xl text-dark-warning dark:text-light-warning mb-4
  }
  
  }

    .info {
  @apply border-dark-info border-5 bg-light-info p-6 bg-opacity-15 border-opacity-15;
  
  h1 {
    @apply text-2xl text-light-info dark:text-dark-info mb-4
  }
  }
</style>

