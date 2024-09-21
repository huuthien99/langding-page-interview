<script setup>
import { ref, onMounted, onUnmounted, watch, provide } from "vue";
import { RouterLink, RouterView } from "vue-router";
import HeroContainer from "@/components/header/HeroContainer.vue";
</script>

<template>
  <RouterView />
</template>

<style scoped></style>
