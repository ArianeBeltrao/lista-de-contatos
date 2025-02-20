<script setup lang="ts">
import { Button } from "@/components/ui/button";
import {
  FormControl,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form";
import { Input } from "@/components/ui/input";
import { toast } from "@/components/ui/toast";

import { toTypedSchema } from "@vee-validate/zod";
import { useForm } from "vee-validate";
import { h } from "vue";
import * as z from "zod";

useHead({
  title: "Agenda | Login",
});

definePageMeta({
  layout: "auth",
});

const formSchema = toTypedSchema(
  z.object({
    username: z.string().min(2).max(50),
    password: z.string().min(2).max(50),
  })
);

const { handleSubmit } = useForm({
  validationSchema: formSchema,
});

const onSubmit = handleSubmit((values) => {
  toast({
    title: "You submitted the following values:",
    description: h(
      "pre",
      { class: "mt-2 w-[340px] rounded-md bg-slate-950 p-4" },
      h("code", { class: "text-white" }, JSON.stringify(values, null, 2))
    ),
  });
  console.log("test onsubmit");
});
</script>

<template>
  <div
    class="flex flex-col bg-gray-100 gap-10 rounded-2xl m-4 w-full sm:w-[600px] sm:h-[450px] py-8 px-4 sm:p-10"
  >
    <NuxtLink class="flex justify-center gap-4 items-center" to="/">
      <i class="pi pi-user text-stone-700" style="font-size: 2.5rem"></i>
      <h1 class="flex font-[Comfortaa] text-3xl text-stone-700">agenda</h1>
    </NuxtLink>
    <form
      class="flex flex-col justify-between h-full gap-6"
      @submit.prevent="onSubmit"
    >
      <div class="flex flex-col sm:gap-6">
        <FormField v-slot="{ componentField }" name="username">
          <FormItem>
            <FormLabel>Usuário</FormLabel>
            <FormControl>
              <Input
                type="text"
                placeholder="Insira seu usuário"
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
              <Input
                type="text"
                placeholder="Insira sua senha"
                v-bind="componentField"
              />
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>
      </div>
      <Button
        type="submit"
        class="w-full bg-sky-200 text-stone-700 hover:bg-sky-300 cursor-pointer"
      >
        Login
      </Button>
    </form>
  </div>
</template>
