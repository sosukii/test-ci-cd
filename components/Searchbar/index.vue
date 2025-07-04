<template>
  <div :class="wrapper">
    <Icon name="tdesign:search" :class="icon" />
    <Input type="text" placeholder="Поиск" :class="input" />
  </div>
</template>

<script setup lang="ts">
const { wrapper, icon, input } = useCssModule()
</script>

<style module lang="scss">
.wrapper {
  position: relative;
  .icon {
    color: grey;
    position: absolute;
    left: 10%;
    top: 50%;
    transform: translate(-50%,-50%);
  }
  .input {
    padding-left: 70px;
    padding-right: 20px;
    padding-top: 8px;
    padding-bottom: 8px;
    border: 2px solid gray;
    border-radius: 90px;
    min-width: 295px;
    @media (min-width: 1280px) {
      padding-top: 18px;
      padding-bottom: 18px;
    }
    @media (min-width: 1440px) {
      min-width: 490px;
    }
  }
}
</style>