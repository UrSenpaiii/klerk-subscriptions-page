<template>
  <header class="flex flex-col items-center gap-y-7 sm:gap-y-6">
    <a href="https://www.klerk.ru/">
      <img src="../assets/logo.svg" alt="logo"/>
    </a>

    <div class="flex gap-x-2 text-secondary leading-4">
      <span class="cursor-pointer hover:text-gray-500 border-b border-slate-300">Главная</span>
      →
      <span class="cursor-pointer hover:text-gray-500 border-b border-slate-300">Рассылки</span>
      →
      <span class="cursor-pointer hover:text-gray-500 border-b border-slate-300">Хлебные крошки</span>
    </div>

    <h1 class="text-4xl sm:text-6xl font-medium">Подписки «Клерка»</h1>

    <div class="flex justify-between gap-x-6 text-base text-[#666] ">
      <div class="flex flex-col gap-y-3.5 cursor-pointer">
        <a class="text-[#5A8CF1] font-medium" href="#">Рассылки</a>
        <span class="border-b border-2 border-[#5A8CF1]"/>
      </div>
      <div class="flex flex-col cursor-pointer">
        <a href="#">Соцсети</a>
      </div>
      <div class="flex flex-col cursor-pointer">
        <a href="#">Мессенджеры</a>
      </div>
    </div>
  </header>
</template>
