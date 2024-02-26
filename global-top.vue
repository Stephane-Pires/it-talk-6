<script setup lang="ts">
import { computed, ref } from 'vue'
import { useTimer } from './setup/utils'

const { timer, passed } = useTimer()
const readValue = ref(false)
let isRead = computed({
  get: () => readValue.value,
  set: (val) => {
    readValue.value = val
  }
})

const showTimerMessage =  computed(() => passed.value > $slidev.configs.presentationTimer.end && !readValue.value)

function wasRead () {
  isRead.value = true
}

</script>

<template>
  <header
    class="absolute top-0 p-2 text-sm w-full h-6"
  >

  <div class="top-0 left-0 opacity-95 absolute h-132 w-245 w-full bg-main border-light-warning dark:border-dark-warning border-3 justify-center flex items-center"
  v-if="showTimerMessage"
  >
<div class="flex flex-col">
  <div
  class=" text-light-warning dark:text-dark-warning font-bold text-4xl"
  >{{$slidev.configs.presentationTimer.message}} {{ timer }}

</div>

<button class="mt-10 bg-light-warning dark:bg-dark-warning w-25 h-10 rounded-3xl m-auto"
@click="() => {
  wasRead()
  }"
>Ok</button>
</div>
</div>
    </header>
</template>