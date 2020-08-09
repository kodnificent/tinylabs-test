<template>
  <header class="bg-white h-18 pl-2 pr-8 w-full flex items-center shadow fixed top-0 left-0">
    <div>
      <img src="/logo.jpg" alt="getchange logo">
    </div>

    <!-- eslint-disable-next-line -->
    <div class="flex-grow"></div>

    <!-- eslint-disable-next-line -->
    <div class="w-9 h-9 rounded-full bg-gray-600"></div>

    <div class="ml-2 hidden md:block">
      <span class="font-medium inline-block">
        Hi, Joshua
      </span>
      <button class="inline-block ml-2">
        <chevron-down-icon class="text-dark-accent" />
        <span class="sr-only">open menu</span>
      </button>
    </div>
  </header>
</template>
