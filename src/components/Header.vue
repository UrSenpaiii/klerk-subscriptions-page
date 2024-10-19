<template>
  <header class="flex flex-col items-center gap-y-6">
    <a href="https://www.klerk.ru/">
      <img src="../assets/logo.svg" alt="logo"/>
    </a>

    <div class="flex gap-x-2 text-secondary leading-4">
      <span class="cursor-pointer hover:text-gray-500">Хлебные крошки</span>
      →
      <span class="cursor-pointer hover:text-gray-500">Хлебные крошки</span>
      →
      <span class="cursor-pointer hover:text-gray-500">Хлебные крошки</span>
    </div>

    <h1 class="text-6xl font-medium">Подписки «Клерка»</h1>

    <div class="flex justify-between gap-x-6 text-base text-[#666] ">
      <div class="flex flex-col hover:text-blue-200 cursor-pointer">
        <a class="text-[#5A8CF1] font-medium" href="#">Рассылки</a>
        <span class="mt-[18px] border-b border-2 border-[#5A8CF1]"/>
      </div>
      <div class="flex flex-col hover:bg-neutral-100 cursor-pointer">
        <a href="#">Соцсети</a>
      </div>
      <div class="flex flex-col hover:bg-neutral-100 cursor-pointer">
        <a href="#">Мессенджеры</a>
      </div>
    </div>
  </header>
</template>
