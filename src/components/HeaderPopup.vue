<template>
  <div class="header-popup-container">
    <div style="position: relative"><Select isBorder="true"></Select></div>
    <img
      @click="$emit('handleToggleMenu')"
      class="menu-mobile"
      src="@/assets/icon/CloseMenu.svg"
      alt=""
    />
  </div>
  <div class="nav-link">
    <div
      v-for="(item, index) in dataHeader"
      :key="index"
      @click="handleClick(item.href)"
      class="link-item"
      :class="{ active: isActive(item.href) }"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Select from "../components/common/Select.vue";
import { useRouter } from "vue-router";

const router = useRouter();
const isActive = (path) => {
  return router.currentRoute.value.path === path;
};

const emit = defineEmits(["handleToggleMenu"]);

const handleClick = (val) => {
  router.push(val);
  emit("handleToggleMenu");
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
.header-popup-container {
  display: flex;
  justify-content: space-between;
  padding: 16px 16px 40px;
}
.menu-mobile {
  cursor: pointer;
}

.nav-link {
  display: flex;
  flex-direction: column;
  padding: 0 16px;
}

.link-item {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 700;
  line-height: 66px;
  width: 100%;
  text-align: center;
  height: 66px;
  cursor: pointer;
}

.link-item:not(:last-child) {
  border-bottom: 1px solid #eeeeee;
}

.active {
  color: #079bee;
}
</style>
