<template>
  <div
    :style="{
      border: isBorder ? '1px solid #AFAFAF' : '',
      backgroundColor: isBorder ? '#F6F6F6' : '',
      borderRadius: isBorder ? '8px' : '',
      padding: isBorder ? '4px 12px' : '',
    }"
    class="select-default"
  >
    <img v-if="language == 'EN'" src="@/assets/icon/eng.svg" alt="" he />
    <img v-else src="@/assets/icon/viet.svg" alt="" />
    <div @click.stop="handleClick" class="icon-down">
      <img v-if="!isBorder" src="@/assets/icon/down.svg" alt="" />
      <img v-else src="@/assets/icon/DownBlack.svg" alt="" />
    </div>
  </div>
  <div
    :style="{ left: isBorder ? '0' : '' }"
    v-show="isShowModel"
    class="model"
    ref="modalRef"
  >
    <div @click="handleChange('VIE')" class="item">
      <img
        style="padding-right: 4px"
        :style="{ visibility: language == 'VIE' ? '' : 'hidden' }"
        src="@/assets/icon/checked.svg"
        alt=""
      />
      <img src="@/assets/icon/viet.svg" alt="" />
      <p>Vietnamese</p>
    </div>
    <hr style="margin: 0 8px" />
    <div @click="handleChange('EN')" class="item">
      <img
        style="padding-right: 4px"
        :style="{ visibility: language == 'EN' ? '' : 'hidden' }"
        src="@/assets/icon/checked.svg"
        alt=""
      />
      <img src="@/assets/icon/eng.svg" alt="" />
      <p>English</p>
    </div>
  </div>
</template>

<script setup>
import { ref, inject, onMounted, onBeforeUnmount } from "vue";

const isShowModel = ref(false);
const modalRef = ref(null);
defineProps({
  isBorder: {
    type: Boolean,
    default: false,
  },
});
const { language, emitLanguage } = inject("language");

const handleClick = () => {
  isShowModel.value = !isShowModel.value;
};

const handleChange = (lang) => {
  emitLanguage(lang);
  handleClick();
};

// Hàm xử lý click bên ngoài modal
const handleClickOutside = (event) => {
  if (
    isShowModel.value &&
    modalRef.value
    //  && !modalRef.value.contains(event.target)
  ) {
    isShowModel.value = false; // Tắt modal nếu click bên ngoài
  }
};

onMounted(() => {
  window.addEventListener("click", handleClickOutside);
});

onBeforeUnmount(() => {
  window.removeEventListener("click", handleClickOutside);
});
// end
</script>

<style lang="css" scoped>
.select-default {
  display: flex;
  align-items: center;
  gap: 4px;
  /* position: relative; */
}
.icon-down {
  cursor: pointer;
}

.item {
  display: flex;
  align-items: center;
  padding: 8px;
  gap: 4px;
  cursor: pointer;
}

p {
  font-size: 10px;
  font-family: "Montserrat";
  font-weight: 700;
}

.model {
  width: 156px;
  background-color: #ffffff;
  border: 1px solid #eeeeee;
  border-radius: 8px;
  position: absolute;
  right: 0;
  z-index: 1;
}
</style>
