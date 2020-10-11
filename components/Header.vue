<template>
  <div
    :class="
      isScroll === 0
        ? 'header'
        : isScroll === 1
        ? 'header-scroll-show'
        : 'header-scroll-hide'
    "
  >
    <div class="header__container">
      <div class="header__container__logo">
        <img :src="imgLogoHeader" alt="logo header" />
      </div>
      <div class="header__container__nav">
        <ul class="header__container__nav__list">
          <li
            class="header__container__nav__list__item header__container__nav__list--active"
          >
            <n-link :to="`/`">Home</n-link>
          </li>
          <li><n-link :to="`/abouts/`">About us</n-link></li>
          <li><a href="">Menu</a></li>
          <li><a href="">Galllery</a></li>
          <li><a href="">Blog</a></li>
          <li><a href="">Contact</a></li>
        </ul>
        <div class="header__container__nav__reservation">
          <button>Reservation</button>
        </div>
        <div class="header__container__nav__menu">
          <img @click="showNav" :src="imgMenu" alt="" />
        </div>
      </div>
      <div
        class="header__container__hide"
        :class="{
          'header__container__menu-reponsive': isNav,
          'header__container__menu-hide': !isNav,
        }"
      >
        <ul class="header__container__menu-reponsive__list">
          <li
            class="header__container__menu-reponsive__list__item header__container__menu-reponsive__list--active"
          >
            <a href="">Home</a>
          </li>
          <li><a href="">About us</a></li>
          <li><a href="">Menu</a></li>
          <li><a href="">Galllery</a></li>
          <li><a href="">Blog</a></li>
          <li><a href="">Contact</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import imgLogoHeader from "../assets/img/Logo_White.png";
import imgMenu from "../assets/img/menu.svg";
export default {
  name: "headers",
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  data: () => {
    return {
      imgLogoHeader,
      imgMenu,
      isNav: false,
      isScroll: 0,
    };
  },
  methods: {
    showNav() {
      this.isNav = !this.isNav;
    },
    handleScroll() {
      if (window.top.scrollY >= 10) {
        this.isScroll = 1;
      } else {
        this.isScroll = 2;
      }
    },
  },
};
</script>

<style lang="scss">
@import "~/assets/scss/layout/header.scss";
</style>

