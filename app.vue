<script setup lang="ts">
import { ref } from "vue";
import Header from "./components/Header.vue";
import Sidebar from "./components/Header.vue";
import Contacts from "./pages/contacts/index.vue";
import { NuxtLayout } from "#components";

const showSidebar = ref(true);

const toggleSidebar = () => {
  showSidebar.value = !showSidebar.value;
};
</script>

<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>
