<script lang="ts" setup>
import { Dialog, DialogContent, DialogTrigger } from "../components/ui/dialog";
import {
  Drawer,
  DrawerClose,
  DrawerContent,
  DrawerTrigger,
} from "../components/ui/drawer";
import { createReusableTemplate, useMediaQuery } from "@vueuse/core";
import { ref } from "vue";

// Reuse `form` section
const [UseTemplate, GridForm] = createReusableTemplate();
const isDesktop = useMediaQuery("(min-width: 768px)");

const isOpen = ref(false);

defineProps({
  title: String,
});
</script>

<template>
  <UseTemplate>
    <div class="flex flex-col justify-between w-full items-center gap-14">
      <h1 class="text-stone-700 text-2xl">{{ title }}?</h1>
      <div class="flex gap-4 w-full">
        <DrawerClose as-child>
          <Button
            class="cursor-pointer border-2 border-sky-200 bg-white text-stone-700 hover:bg-sky-300 w-full"
          >
            Cancelar
          </Button>
        </DrawerClose>

        <Button
          class="cursor-pointer bg-sky-200 text-stone-700 hover:bg-sky-300 w-full"
        >
          Excluir
        </Button>
      </div>
    </div>
  </UseTemplate>

  <Dialog v-if="isDesktop" v-model:open="isOpen">
    <DialogTrigger as-child>
      <i class="pi pi-trash cursor-pointer" style="font-size: 1rem"></i>
    </DialogTrigger>
    <DialogContent class="sm:max-w-[425px] bg-white">
      <GridForm />
    </DialogContent>
  </Dialog>

  <Drawer v-else v-model:open="isOpen">
    <DrawerTrigger as-child>
      <i class="pi pi-trash cursor-pointer" style="font-size: 1rem"></i>
    </DrawerTrigger>
    <DrawerContent class="bg-white p-6">
      <GridForm />
    </DrawerContent>
  </Drawer>
</template>
