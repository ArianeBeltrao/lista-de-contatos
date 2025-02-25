<script setup lang="ts">
import { useRouter } from "vue-router";

const router = useRouter();

const goToCreatePage = () => {
  router.push("/contatos/criar-contato");
};
</script>

<template>
  <div
    class="px-6 py-4 items-end flex w-full h-full relative z-0 bg-stone-200 flex-col rounded-2xl gap-10"
  >
    <div class="flex justify-between w-full items-center">
      <h1 class="text-stone-700 text-2xl">Contatos</h1>

      <Button
        @click="goToCreatePage"
        class="cursor-pointer bg-sky-200 text-stone-700 hover:bg-sky-300"
      >
        Criar novo contato
      </Button>
    </div>

    <div class="relative w-full max-w-sm items-center">
      <Input id="search" type="text" placeholder="Search..." class="pl-10" />
      <span
        class="absolute start-0 inset-y-0 flex items-center justify-center px-2"
      >
        <i class="pi pi-search" style="font-size: 1rem"></i>
      </span>
    </div>

    <ContactsTable />
  </div>
</template>
