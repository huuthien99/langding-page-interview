<template>
  <div class="input-wrap">
    <input type="text" placeholder="Enter your email" />
    <slot></slot>
  </div>
</template>

<script setup></script>

<style lang="css" scoped>
.input-wrap {
  background: #ffffff;
  width: calc(100% - 28px);
  padding: 0 14px;
  height: 56px;
  display: flex;
  align-items: center;
  border-radius: 8px;
  justify-content: space-between;
  border: 1px solid #ffffff;
}
input {
  border: none;
  outline: none;
  line-height: 56px;
  height: 100%;
  width: 100%;
  padding-right: 10px;
}
</style>
