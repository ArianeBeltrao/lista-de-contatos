<script setup lang="ts">
import { useRouter } from "vue-router";

const router = useRouter();
const goToEditPage = () => {
  router.push("/pessoas/criar-pessoa");
};
</script>

<template>
  <div
    class="px-6 py-4 flex items-center w-full h-full relative z-0 bg-stone-200 flex-col rounded-2xl gap-10"
  >
    <div class="flex justify-between w-full items-center">
      <h1 class="text-stone-700 text-2xl">Pessoas</h1>

      <Button
        @click="goToEditPage"
        class="cursor-pointer bg-sky-200 text-stone-700 hover:bg-sky-300"
      >
        Cadastrar nova pessoa
      </Button>
    </div>

    <PersonTable />
  </div>
</template>
