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
  title: "Agenda | Cadastrar pessoa",
});

const router = useRouter();

const goBack = () => {
  router.push("/pessoas");
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
      <h1 class="text-stone-700 text-2xl items-center">
        Cadastrar nova pessoa
      </h1>
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
          <FormField v-slot="{ componentField }" name="cpf">
            <FormItem class="w-full">
              <FormLabel>CPF</FormLabel>
              <FormControl>
                <Input type="text" placeholder="CPF" v-bind="componentField" />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
        </div>

        <div class="flex sm:gap-4 flex-col sm:flex-row">
          <FormField v-slot="{ componentField }" name="logradouro">
            <FormItem class="w-full">
              <FormLabel>Logradouro</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Logradouro"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
          <FormField v-slot="{ componentField }" name="numero">
            <FormItem class="w-full">
              <FormLabel>Número</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Número"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
          <FormField v-slot="{ componentField }" name="bairro">
            <FormItem class="w-full">
              <FormLabel>Bairro</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Bairro"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
        </div>
        <div class="flex sm:gap-4 flex-col sm:flex-row">
          <FormField v-slot="{ componentField }" name="cidade">
            <FormItem>
              <FormLabel>Cidade</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Cidade"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
          <FormField v-slot="{ componentField }" name="estado">
            <FormItem>
              <FormLabel>Estado</FormLabel>
              <FormControl>
                <Input
                  type="text"
                  placeholder="Estado"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
            <FormField v-slot="{ componentField }" name="cep">
              <FormItem>
                <FormLabel>CEP</FormLabel>
                <FormControl>
                  <Input
                    type="text"
                    placeholder="CEP"
                    v-bind="componentField"
                  />
                </FormControl>
                <FormMessage />
              </FormItem>
            </FormField>
            <FormField v-slot="{ componentField }" name="pais">
              <FormItem>
                <FormLabel>País</FormLabel>
                <FormControl>
                  <Input
                    type="text"
                    placeholder="País"
                    v-bind="componentField"
                  />
                </FormControl>
                <FormMessage />
              </FormItem>
            </FormField>
          </FormField>
        </div>
        <div class="flex sm:gap-4 flex-col sm:flex-row">
          <FormField v-slot="{ componentField }" name="cep">
            <FormItem>
              <FormLabel>Foto</FormLabel>
              <FormControl>
                <Input type="text" placeholder="Foto" v-bind="componentField" />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>
        </div>
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
