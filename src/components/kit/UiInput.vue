<script setup lang="ts">
defineProps<{
  placeholder: string,
  btnLabel: string
}>()
</script>

<template>
  <div class="relative w-full">
    <input type="email" :placeholder="placeholder"
           class="text-base text-gray-900 placeholder-[#666] p-4 rounded-l-lg focus:ring-2 ring-inset block w-11/12">
    <button type="submit"
            class="text-white absolute end-0 bottom-0 bg-[#316FEE] hover:bg-blue-600 ring-inset focus:ring-2 focus:ring-blue-300 rounded-full text-base px-8 py-4"
    >{{btnLabel}}</button>
  </div>
</template>
