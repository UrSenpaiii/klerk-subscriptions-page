<script setup lang="ts">
import {ref} from "vue";

type Sizes = { sm: String, md: String }

const {size = 'md'} = defineProps<{
  label: String
  size?: keyof Sizes,
}>()

const model = defineModel()

const sizes = ref<Sizes>({
  sm: "w-8 h-4 after:w-3.5 after:h-3.5",
  md: "w-12 h-6 after:w-[22px] after:h-[22px]"
})
</script>

<template>
  <label class="inline-flex items-center cursor-pointer">
    <input type="checkbox" class="sr-only peer" v-model="model">

    <div :class="sizes[size]"
         class="relative rounded-full after:transition-all
                bg-[#DCDCDC] after:bg-white peer-checked:bg-[#316FEE]
                peer peer-focus:ring-2 peer-checked:after:translate-x-full
                after:content-[''] after:absolute after:top-[1px] after:start-[2px] after:rounded-full"
    />

    <span class="ms-2 text-sm">{{ label }}</span>
  </label>
</template>
