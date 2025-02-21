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
  title: "Agenda | Criar usuário",
});

const router = useRouter();

const goBack = () => {
  router.push("/usuarios");
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
      <h1 class="text-stone-700 text-2xl items-center">Criar novo usuário</h1>
    </div>

    <form
      class="flex flex-col h-full w-full overflow-auto px-2 justify-between"
    >
      <div class="flex flex-col gap-3">
        <div class="flex sm:gap-4 flex-col sm:flex-row">
          <FormField v-slot="{ componentField }" name="name">
            <FormItem class="w-full">
              <FormLabel>Nome</FormLabel>
              <FormControl>
                <Input type="text" placeholder="Nome" v-bind="componentField" />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
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
        </div>

        <div class="flex sm:gap-4 flex-col sm:flex-row">
          <FormField v-slot="{ componentField }" name="cpf">
            <FormItem class="w-full">
              <FormLabel>CPF</FormLabel>
              <FormControl>
                <Input type="text" placeholder="CPF" v-bind="componentField" />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
          <FormField v-slot="{ componentField }" name="phone">
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
          <FormField v-slot="{ componentField }" name="date">
            <FormItem class="w-full">
              <FormLabel>Data de nascimento</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Data de nascimento"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
        </div>
        <FormField v-slot="{ componentField }" name="username">
          <FormItem>
            <FormLabel>Usuário</FormLabel>
            <FormControl>
              <Input
                type="text"
                placeholder="Usuário"
                v-bind="componentField"
              />
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>
        <FormField v-slot="{ componentField }" name="password">
          <FormItem>
            <FormLabel>Senha</FormLabel>
            <FormControl>
              <Input type="text" placeholder="Senha" v-bind="componentField" />
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
