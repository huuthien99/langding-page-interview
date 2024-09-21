<template>
  <HeroContainer @onChangeLangue="onChangeLangue"></HeroContainer>
  <div @click="handleScroll" class="arrow-scroll">
    <img v-if="isScrolled" src="@/assets/icon/ArrowUp.svg" alt="" />
    <img v-else src="@/assets/icon/ArrowDown.svg" alt="" />
  </div>
  <slot></slot>
  <Footer></Footer>
</template>

<script setup>
import { ref, onMounted, onUnmounted, watch, provide } from "vue";
import { RouterLink, RouterView } from "vue-router";
import HeroContainer from "@/components/header/HeroContainer.vue";
import Footer from "@/components/footer/Footer.vue";

const isScrolled = ref(false);
const scrollPosition = ref(0);
const language = ref("EN");

const onChangeLanguage = (val) => {
  language.value = val;
};

provide("language", {
  language,
  emitLanguage: onChangeLanguage,
});

watch(scrollPosition, (newValue) => {
  isScrolled.value = newValue > 200;
});

const updateScrollPosition = () => {
  scrollPosition.value = window.scrollY;
};

onMounted(() => {
  window.addEventListener("scroll", updateScrollPosition);
});

onUnmounted(() => {
  window.removeEventListener("scroll", updateScrollPosition);
});

const handleScroll = () => {
  if (isScrolled.value) {
    window.scrollTo({ top: 0, behavior: "smooth" });
  } else {
    window.scrollTo({ top: document.body.scrollHeight, behavior: "smooth" });
  }
};
</script>

<style lang="css" scoped>
.arrow-scroll {
  position: fixed;
  top: 85%;
  right: 0;
  cursor: pointer;
  z-index: 1;
}
</style>
