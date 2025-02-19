<script setup lang="ts">
import { ref } from "vue";
import Contacts from "./contacts/index.vue";

const showSidebar = ref(true);

const toggleSidebar = () => {
  showSidebar.value = !showSidebar.value;
};
</script>

<template>
  <Contacts />
</template>
