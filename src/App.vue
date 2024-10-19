<script setup lang="ts">
import Footer from "@/components/Footer.vue";
import Header from "@/components/Header.vue";

import Card from "@/components/Card.vue";
import UiInput from "@/components/kit/UiInput.vue";
import UiToggle from "@/components/kit/UiToggle.vue";
import {ref} from "vue";

const cardData = ref<Array<Object>>([{
  sendTime: "Перед рассветом",
  title: "Утренний бухгалтер",
  description: "Самые важные новости и события за день. Кратко, по делу, структурировано.",
  features: ["Новости для бухгалтеров, ИП и директора", "Подборка статей за день"],
  subscribers: 59342,
  imgPath: "/src/assets/img/Frame%203505.png"
}, {
  sendTime: "После заката",
  title: "Ночной бухгалтер",
  description: "Самая краткая газета о налогах и бухучете в мире — современная рассылка для чтения.",
  features: ["Анализ, оценка и только самое главное", "Лучшие комменты юзеров в обзоре"],
  subscribers: 37480,
  imgPath: "/src/assets/img/Frame%203507.png"
}, {
  sendTime: "Раз в две недели",
  title: "Ножницы скидок",
  description: "Подборка самых выгодных и полезных спецпредложений от надежных компаний.",
  features: ["Акции и скидки от лидеров рынка", "Те, кто подписался – экономят много денег"],
  subscribers: 92118,
  imgPath: "/src/assets/img/Frame%203509.png"
}, {
  sendTime: "По мере появления анонсов",
  title: "Чемодан вебинаров",
  description: "Подборка с анонсами бесплатных вебинаров на самые топовые темы при участии экспертов.",
  features: ["<span class='font-medium'>Никогда не пришлем платные вебинары\", \"Подборка топовых тем для вебинаров</span>"],
  subscribers: 92082,
  imgPath: "/src/assets/img/Frame%203511.png"
}])

const subscribeToAll = ref(false)

const uncheckSubAll = () => subscribeToAll.value = false
</script>

<template>
  <div class="h-screen w-screen">
    <div class="flex flex-col justify-between h-full items-center py-12 max-w-5xl mx-auto">
      <Header/>
      <main class="h-full w-full bg-[#F5F5F8] rounded-2xl py-12">

        <div class="px-12">
          <div class="font-medium pb-6">Выберите рассылки, которые подходят именно вам</div>
          <div class="flex flex-col items-start gap-y-4">
            <ui-input placeholder="Электронная почта" btn-label="Подписаться"/>

            <ui-toggle v-model="subscribeToAll" size="sm" label="Подписаться на все рассылки"/>
          </div>
        </div>

        <div class="grid grid-cols-2 gap-6 px-6 pt-8">
          <card v-for="(data, i) in cardData" :key="i"
                :send-time="data.sendTime"
                :title="data.title"
                :description="data.description"
                :features="data.features"
                :subscribers="data.subscribers"
                :imgPath="data.imgPath"
                :subscribe-to-all="subscribeToAll"
                @unsubscribed="uncheckSubAll"
          />
        </div>
      </main>

      <Footer/>
    </div>
  </div>

</template>
