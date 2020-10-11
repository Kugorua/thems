<template>
  <div class="customerStore">
    <div class="customerStore__container">
      <ul class="customerStore__container__dots">
        <li
          class="customerStore__container__dots__item"
          @click.prevent="slideTo(0)"
          :class="{
            customerStore__container__dots__active: dataCustomer[0].state,
          }"
        >
          <span></span>
        </li>
        <li
          class="customerStore__container__dots__item"
          @click.prevent="slideTo(1)"
          :class="{
            customerStore__container__dots__active: dataCustomer[1].state,
          }"
        >
          <span></span>
        </li>

        <li
          class="customerStore__container__dots__item"
          @click.prevent="slideTo(2)"
          :class="{
            customerStore__container__dots__active: dataCustomer[2].state,
          }"
        >
          <span></span>
        </li>
        <li
          class="customerStore__container__dots__item"
          @click.prevent="slideTo(3)"
          :class="{
            customerStore__container__dots__active: dataCustomer[3].state,
          }"
        >
          <span></span>
        </li>
        <li
          class="customerStore__container__dots__item"
          @click.prevent="slideTo(4)"
          :class="{
            customerStore__container__dots__active: dataCustomer[4].state,
          }"
        >
          <span></span>
        </li>
      </ul>
      <div class="customerStore__container__title">
        <div class="customerStore__container__title__line"></div>
        <p>testimonials</p>
        <h2>Customer stories</h2>
      </div>
      <div class="customerStore__container__slider">
        <hooper
          :infiniteScroll="true"
          style="height: 350px; outline: none"
          ref="carousel"
          @slide="updateCarousel"
        >
          <slide
            class="slider"
            v-for="(item, index) in dataCustomer"
            :key="index"
          >
            <div class="slider__container">
              <div
                class="slider__container__infor"
                :class="{
                  slider__container__hover: dataCustomer[index].state,
                }"
              >
                <img :src="item.avatar" alt="" />
                <p>"</p>
                <p>
                  {{ item.infor }}
                </p>
                <p class="slider__container__infor__name">{{ item.name }}</p>
              </div>
              <div class="slider__container__item">
                <div class="slider__container__item__avatar"></div>
              </div>
            </div>
          </slide>
        </hooper>
      </div>
    </div>
  </div>
</template>

<script>

import imgAvatar from "../../../assets/img/avatar.png";
let dataCustomer = [
  {
    avatar: imgAvatar,
    infor:
      "So that for better or for worse, we two, for the time, were wedded; and should poor Queequeg sink to rise no more, then both usage and honour demanded was my own.",
    name: "Jeffrey Weaver",
    state: true,
  },
  {
    avatar: imgAvatar,
    infor:
      "So that for better or for worse, we two, for the time, were wedded; and should poor Queequeg sink to rise no more, then both usage and honour demanded was my own.",
    name: "Jeffrey Weaver",
    state: false,
  },
  {
    avatar: imgAvatar,
    infor:
      "So that for better or for worse, we two, for the time, were wedded; and should poor Queequeg sink to rise no more, then both usage and honour demanded was my own.",
    name: "Jeffrey Weaver",
    state: false,
  },
  {
    avatar: imgAvatar,
    infor:
      "So that for better or for worse, we two, for the time, were wedded; and should poor Queequeg sink to rise no more, then both usage and honour demanded was my own.",
    name: "Jeffrey Weaver",
    state: false,
  },
  {
    avatar: imgAvatar,
    infor:
      "So that for better or for worse, we two, for the time, were wedded; and should poor Queequeg sink to rise no more, then both usage and honour demanded was my own.",
    name: "Jeffrey Weaver",
    state: false,
  },
];
export default {
  
  methods: {
    slideTo(item) {
      this.$refs.carousel.slideTo(item);
    },
    updateCarousel(payload) {
      this.carouselData = payload.currentSlide;
      if (payload.currentSlide === 5) {
        this.carouselData = 0;
      } else if (this.carouselData === -1) {
        this.carouselData = 4;
      }
      this.dataCustomer = this.dataCustomer.map((item, index) => {
        if (index === this.carouselData) {
          return { ...item, state: true };
        }
        return { ...item, state: false };
      });
    },
  },
  data: () => {
    return {
      imgAvatar,
      dataCustomer,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "~/assets/scss/components/home-pages/_customer-sotre.scss";

.customerStore {
  background-image: url("../../../assets/img/Testimonials.png");
}
@keyframes showCustomer {
  0% {
    transform: scale(1.5, 1.5);
  }
  100% {
    transform: scale(1, 1);
  }
}
</style>