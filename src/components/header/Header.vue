<template>
  <header class="wrapper">
    <RouterLink to="/" class="link-logo">
      <img alt="logo" class="logo" src="@/assets/logo.svg" />
    </RouterLink>
    <nav class="nav-link">
      <RouterLink
        v-for="(item, index) in dataHeader"
        :key="index"
        :to="item.href"
        class="link-item"
        :style="{ color: isActive(item.href) ? '#079bee' : '' }"
      >
        {{ item.name }}
      </RouterLink>
      <div style="position: relative">
        <Select></Select>
      </div>
    </nav>
    <img
      @click.stop="handleToggleMenu"
      class="menu-mobile"
      src="@/assets/icon/OpenMenu.svg"
      alt=""
    />
    <div class="header-popup" :class="{ toggle: isToggle }">
      <HeaderPopup @handleToggleMenu="handleToggleMenu" />
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";
import Select from "../common/Select.vue";
import HeaderPopup from "../HeaderPopup.vue";
import { RouterLink, useRoute } from "vue-router";
const router = useRoute();
const isToggle = ref(false);

const isActive = (path) => {
  return router.path === path;
};

const handleToggleMenu = () => {
  isToggle.value = !isToggle.value;
};

const dataHeader = ref([
  {
    name: "ABOUT US",
    href: "/about",
  },
  {
    name: "GAMES",
    href: "/games",
  },
  {
    name: "PARTNERS",
    href: "/partners",
  },
  {
    name: "CONTACT US",
    href: "/contact-us",
  },
]);
</script>

<style lang="css" scoped>
@media (min-width: 1366px) {
  .wrapper {
    display: flex;
    justify-content: space-between;
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 10;
    padding-top: 20px;
    padding-bottom: 20px;
    background: linear-gradient(
      180deg,
      rgba(0, 0, 0, 0.5) -25%,
      rgba(0, 0, 0, 0) 100%
    );
  }

  .header-popup {
    display: none;
  }

  .logo {
    width: 108.82px;
    height: 64px;
  }

  .link-logo {
    padding-left: 79px;
  }

  .nav-link {
    padding-top: 20px;
    padding-right: 79px;
    display: flex;
    align-items: center;
  }

  .link-item {
    color: #ffffff;
    text-decoration: none;
    cursor: pointer;
    padding-right: 20px;
    font-family: "Montserrat";
    font-weight: 700;
  }

  .menu-mobile {
    display: none;
  }
}
@media (min-width: 357px) and (max-width: 1365px) {
  .wrapper {
    padding: 44px 16px 24px;
    display: flex;
    justify-content: space-between;
    background: linear-gradient(
      180deg,
      rgba(0, 0, 0, 0.5) -25%,
      rgba(0, 0, 0, 0) 100%
    );
    position: sticky;
    top: 0;
    z-index: 10;
  }
  .nav-link {
    display: none;
  }

  .menu-mobile {
    display: block;
    cursor: pointer;
  }

  .header-popup {
    position: fixed;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;
    background-color: white;
    transition: transform 0.3s ease-in-out;
    transform: translateX(100%);
    z-index: 3;
  }
  .toggle {
    transform: translateX(0);
  }
}
</style>
