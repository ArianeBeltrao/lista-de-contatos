<script setup lang="ts">
import { useRouter } from "vue-router";
import { Button } from "@/components/ui/button";
import {
  FormControl,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form";
import { Input } from "@/components/ui/input";

useHead({
  title: "Agenda | Criar contato",
});

const router = useRouter();

const goBack = () => {
  router.push("/contatos");
};
</script>

<template>
  <div
    class="px-6 py-4 flex w-full flex-1 relative z-0 bg-stone-200 flex-col rounded-2xl overflow-auto mt-3 sm:mt-0"
  >
    <div class="flex items-center mb-3 gap-3">
      <button
        @click="goBack"
        class="flex cursor-pointer items-center justify-center text-stone-700 hover:bg-sky-300 rounded-full h-10 w-10"
      >
        <i class="pi pi-angle-left cursor-pointer" style="font-size: 1rem"></i>
      </button>
      <h1 class="text-stone-700 text-2xl items-center">Criar novo contato</h1>
    </div>

    <form
      class="flex flex-col h-full w-full overflow-auto px-2 justify-between"
    >
      <div class="flex gap-4 flex-col sm:gap-6">
        <div class="flex gap-4 flex-col sm:flex-row">
          <FormField v-slot="{ componentField }" name="tag">
            <FormItem class="w-full">
              <FormLabel>Tag</FormLabel>
              <FormControl>
                <Input type="text" placeholder="Tag" v-bind="componentField" />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>

          <FormField v-slot="{ componentField }" name="tipoContato">
            <FormItem class="w-full">
              <FormLabel>Tipo de contato</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Tipo de contato"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
        </div>

        <div class="flex gap-4 flex-col sm:flex-row">
          <FormField v-slot="{ componentField }" name="email">
            <FormItem class="w-full">
              <FormLabel>Email</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Email"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
          <FormField v-slot="{ componentField }" name="telefone">
            <FormItem class="w-full">
              <FormLabel>Telefone</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Telefone"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
        </div>

        <FormField v-slot="{ componentField }" name="privado">
          <FormItem class="w-full">
            <FormLabel>Privado</FormLabel>
            <FormControl>
              <div class="flex items-center space-x-2">
                <Checkbox id="remember" v-bind="componentField" />
                <label class="text-sm font-medium"> Sim </label>
              </div>
              <div class="flex items-center space-x-2">
                <Checkbox id="remember" v-bind="componentField" />
                <label class="text-sm font-medium"> Não </label>
              </div>
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>
      </div>
      <Button
        type="submit"
        class="w-full bg-sky-200 text-stone-700 hover:bg-sky-300 cursor-pointer my-4"
      >
        Salvar
      </Button>
    </form>
  </div>
</template>
