<template>
  <div class="container">
    <div :class="wrapper">
      <span :class="title">MUHOMORNIA</span>

      <!-- desktop -->
      <div :class="desktop">
        <Searchbar />
        <a :href="`tel:${PHONE}`" :class="[phone, desktopPhone]">{{ PHONE }}</a>
        <Icon 
          :name="isUserIconHovered ? 'tdesign:cat-filled' : 'tdesign:cat'"
          :class="user" 
          @mouseenter="isUserIconHovered = true"
          @mouseleave="isUserIconHovered = false"
        />
        <div :class="desktopSwitcher"> 
          <span :class="[switchBtn, ru]">RU</span>/
          <span :class="[switchBtn, eng]">ENG</span>
        </div>
      </div>

      <!-- mobile -->
       <div :class="mobile">
         <Icon name="tdesign:search"/>
         <a :href="`tel:${PHONE}`" :class="phone">{{ PHONE }}</a>
         <Icon name="tdesign:view-list"/>
        </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { PHONE } from '~/utils/constants';
const { wrapper, title, desktop, mobile, 
        phone, desktopPhone, user, 
        desktopSwitcher, switchBtn,  ru, eng
      } = useCssModule();

const isUserIconHovered = ref(false)
</script>

<style module lang="scss">
.wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 45px;
  padding-bottom: 45px;
  .title {
    font-size: 36px;
    height: fit-content;
  }
  .desktop {
    display: none;
    align-items: center;
    @media (min-width: 1000px) {
      display: flex
    }
    &Phone {
      background-color: #1FAB8A;
      color: white;
      font-weight: 700;
      margin-left: 25px;
      margin-right: 25px;
      padding-top: 10px;
      padding-bottom: 10px;
      padding-left: 35px;
      padding-right: 35px;
      border-radius: 90px;
      @media (min-width: 1280px) {
        margin-left: 70px;
        margin-right: 70px;
        padding-top: 20px;
        padding-bottom: 20px;
        padding-left: 60px;
        padding-right: 60px;
        border-radius: 90px;
      }
    }
    .user {
      width: 40px;
      height: 40px;
      &:hover {
        cursor: pointer;
      }
    }
    &Switcher {
      display: none;
      padding-left: 15px;
      @media (min-width: 768px) {
        display: flex;
      }
      @media (min-width: 1280px) {
        padding-left: 40px;
      }
      .switchBtn {
        &:hover {
          cursor: pointer;
          color: #1e40af ;
        }
      }
    }
  }
  .mobile {
    display: flex;
    gap: 20px;
    align-items: center;
    @media (min-width: 480px) {
      gap: 30px;
    }
    @media (min-width: 768px) {
      gap: 60px;
    }
    @media (min-width: 1000px) {
      display: none;
    }
    .phone {
      display: none;
      @media (min-width: 768px) {
        display: flex
      }
    }
  }
}
</style>