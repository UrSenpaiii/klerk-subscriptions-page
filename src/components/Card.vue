<script setup lang="ts">
import Check from "@/components/icons/Check.vue";
import UiToggle from "@/components/kit/UiToggle.vue";
import {computed, ref, watch} from "vue";

const props = defineProps<{
  sendTime: string
  title: string
  description: string
  features: Array<string>
  subscribers: number
  imgPath: string
  subscribeToAll: boolean
}>()
const emits = defineEmits(['unsubscribed'])

const imgUrl = new URL(props.imgPath, import.meta.url).href

const formateSubs = computed(() => props.subscribers.toLocaleString('fr'))

const subscribe = ref(false)

watch(() => props.subscribeToAll, v => subscribe.value ||= v)
watch(() => subscribe.value, v => {
  if (!v) emits('unsubscribed')
})
</script>

<template>
  <div class="bg-white p-6 gap-x-6 rounded-2xl hover:shadow-lg transition-all">
    <div class="grid gap-y-4 text-left">
      <div class="grid grid-cols-4">
        <div class="col-span-3 sm:col-span-3">
          <div class="text-secondary">
            {{ sendTime }}
          </div>
          <div class="text-xl font-medium">
            {{ title }}
          </div>
        </div>

        <div class="sm:row-span-2 justify-self-end max-w-fit">
          <img :src="imgUrl" class="size-10 sm:size-20 rounded-lg" alt="poster">
        </div>

        <p class="col-span-4 sm:col-span-3 pt-2 text-sm text-[#666] max-w-full">
          {{ description }}
        </p>
      </div>

      <div class="grid gap-2 text-sm pb-0 sm:pb-6">
        <div v-for="feature in features" class="flex gap-2 items-center">
          <check/>
          <span v-html="feature"/>
        </div>
      </div>

      <ui-toggle v-model="subscribe" :label="`Уже получает ${formateSubs} человек`"/>
    </div>
  </div>
</template>
