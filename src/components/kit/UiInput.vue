<script setup lang="ts">
import {onMounted, onUnmounted, ref} from "vue";
import ArrowLeft from "@/components/icons/ArrowLeft.vue";

defineProps<{
  placeholder: string,
  btnLabel: string
}>()

onMounted(() => window.addEventListener("resize", onResize))
onUnmounted(() => window.removeEventListener("resize", onResize))

const isMobileSize = ref(window.innerWidth < 640)

const onResize = () => isMobileSize.value = window.innerWidth < 640

</script>

<template>
  <div class="relative w-full">
    <input type="email" :placeholder="placeholder"
           class="text-base text-gray-900 placeholder[#666] p-4 rounded-l-lg focus:ring-2 ring-inset block w-[95%]">
    <button type="submit"
            class="text-white absolute end-0 bottom-0 bg-[#316FEE] hover:bg-blue-600 ring-inset focus:ring-2 focus:ring-blue-300 rounded-full text-base p-4 sm:px-8"
    >
      <arrow-left v-if="isMobileSize"/>
      <span v-else>{{btnLabel}}</span>
    </button>
  </div>
</template>
