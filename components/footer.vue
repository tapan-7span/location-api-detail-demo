<!--
  This example requires some changes to your config:
  
  ```
  // tailwind.config.js
  module.exports = {
    // ...
    plugins: [
      // ...
      require('@tailwindcss/forms'),
    ],
  }
  ```
-->
<template>
  <div
    class="relative isolate overflow-hidden bg-gray-900 py-16 sm:py-24 lg:py-32"
  >
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div
        class="mx-auto grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 lg:max-w-none lg:grid-cols-2"
      >
        <dl
          class="grid grid-cols-1 gap-x-8 gap-y-10 sm:grid-cols-2 lg:pt-2 mx-auto w-full"
        >
          <div class="flex flex-col items-center justify-center text-center">
            <div class="rounded-md bg-white/5 p-2 ring-1 ring-white/10 w-fit">
              <CalendarDaysIcon class="h-6 w-6 text-white" aria-hidden="true" />
            </div>
            <dt class="mt-4 font-semibold text-white">
              Kindly Open Website While You Needs to share your detail 😄
            </dt>
          </div>
          <div class="flex flex-col items-center justify-center">
            <div class="rounded-md bg-white/5 p-2 ring-1 ring-white/10 w-fit">
              <HandRaisedIcon class="h-6 w-6 text-white" aria-hidden="true" />
            </div>
            <dt class="mt-4 font-semibold text-white">No spams Please 🫥</dt>
          </div>
        </dl>
      </div>
    </div>
    <div
      class="absolute left-1/2 top-0 -z-10 -translate-x-1/2 blur-3xl xl:-top-6"
      aria-hidden="true"
    >
      <div class="aspect-[1155/678] w-[72.1875rem] bg-gray-800 opacity-30" />
    </div>
  </div>
</template>

<script setup>
import { CalendarDaysIcon, HandRaisedIcon } from "@heroicons/vue/24/outline";
</script>
