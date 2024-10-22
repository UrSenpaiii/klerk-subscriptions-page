<script setup lang="ts">
import {onMounted, onUnmounted, ref} from "vue";

defineProps<{
  placeholder: string,
  btnLabel: string
}>()

onMounted(() => window.addEventListener("resize", onResize))
onUnmounted(() => window.removeEventListener("resize", onResize))

const isMobile = ref(window.innerWidth < 640)

const onResize = () => isMobile.value = window.innerWidth < 640
</script>

<template>
  <form class="relative w-full">
    <input type="email" :placeholder="placeholder" required
           class="p-4 text-base text-gray-900 placeholder[#666] rounded-l-lg focus:ring-2 ring-inset block w-[95%]">
    <button type="submit"
            class="p-4 sm:px-8 text-white absolute end-0 bottom-0 bg-[#316FEE] hover:bg-blue-600 ring-inset focus:ring-2 focus:ring-blue-300 rounded-full text-base"
    >
      <img v-if="isMobile" src="@/assets/img/icons/ArrowLeft.svg" :alt="btnLabel"/>
      <span v-else>{{ btnLabel }}</span>
    </button>
  </form>
</template>
