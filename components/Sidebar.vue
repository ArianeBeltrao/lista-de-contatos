<script setup lang="ts">
import { useRoute } from "vue-router";

const route = useRoute();

const menuItems = [
  { name: "Contatos", path: "/contatos" },
  { name: "Meu Cadastro", path: "/meu-cadastro" },
  { name: "Usuários", path: "/usuarios" },
  { name: "Pessoas", path: "/pessoas" },
];
</script>

<template>
  <div
    class="w-48 fixed left-0 z-20 sm:flex sm:relative sm:w-72 h-full flex-none sm:justify-between justify-start flex flex-col bg-stone-700 p-4"
  >
    <div class="flex flex-col m-3">
      <NuxtLink
        v-for="item in menuItems"
        :key="item.path"
        :to="item.path"
        class="px-4 py-2 text-white flex w-full hover:bg-sky-200 hover:text-stone-700 rounded-[48px] cursor-pointer"
        :class="{ 'bg-blue-200 !text-stone-700': route.path === item.path }"
        >{{ item.name }}</NuxtLink
      >
    </div>

    <div class="flex">
      <Button
        class="w-full cursor-pointer bg-sky-200 text-stone-700 hover:bg-sky-300"
      >
        Log out
      </Button>
    </div>
  </div>
</template>
