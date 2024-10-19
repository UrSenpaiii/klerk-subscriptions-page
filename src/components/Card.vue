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
  <div class="flex justify-between bg-white p-6 gap-x-6 rounded-2xl hover:shadow-lg transition-all">
    <div class="grid gap-y-4 text-left">
      <div>
        <div class="text-secondary">
          {{ sendTime }}
        </div>
        <div class="text-xl font-medium">
          {{ title }}
        </div>
        <p class="pt-2 text-sm text-[#666]">
          {{ description }}
        </p>
      </div>

      <div class="grid gap-2 text-sm">
        <div v-for="feature in features" class="flex gap-2 items-center">
          <check/>
          <span v-html="feature"/>
        </div>
      </div>

      <ui-toggle v-model="subscribe" :label="`Уже получает ${formateSubs} человек`"/>
    </div>

    <img :src="imgUrl" class="size-20 rounded-lg" alt="poster">
  </div>
</template>
