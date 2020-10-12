<template>
  <div class="chefs">
    <div class="chefs__container">
      <div class="chefs__container__title">
        <div class="chefs__container__title__line"></div>
        <p>Our Team</p>
        <h2>Meet our talent Chefs</h2>
      </div>
      <div class="chefs__container__slider">
        <ul class="chefs__container__slider__dots">
          <li
            class="chefs__container__slider__dots__item"
            :class="{
              'chefs__container__slider__dots__item-active': item.state,
            }"
            v-for="(item, index) in dataSlideItem"
            :key="index"
            @click.prevent="slideTo(index - 1)"
          >
            <span> </span>
          </li>
        </ul>
        <hooper
          ref="carousel"
          :settings="hooperSettings"
          style="height: auto; outline: none"
          @slide="updateCarousel"
        >
          <slide
            class="slider"
            v-for="(item, index) in dataSlideItem"
            :key="index"
          >
            <div class="slider__items">
              <div
                class="slider__container"
                :class="{ 'active-chefs': item.state }"
              >
                <img
                  class="slider__container__img"
                  :class="{ slider__container__act: item.state }"
                  :src="item.img"
                  alt=""
                />
                <div class="slider__container__item">
                  <p class="slider__container__item__price">{{ item.price }}</p>
                  <!-- 1 -->
                  <p class="slider__container__item__name">{{ item.name }}</p>
                </div>
              </div>
            </div>
          </slide>
        </hooper>
      </div>
    </div>
  </div>
</template>

<script>

import imgchefs1 from "../../../assets/img/Chef1.jpg";
import imgchefs2 from "../../../assets/img/Chef2.png";
import imgchefs3 from "../../../assets/img/Chef3.png";
import imgchefs4 from "../../../assets/img/Chef4.png";
let dataSlideItem = [
  { img: imgchefs1, price: "25$", name: "Spaghetti Carbonara", state: false },
  { img: imgchefs2, price: "45$", name: "Spaghetti Carbonara", state: true },
  { img: imgchefs3, price: "35$", name: "Spaghetti Carbonara", state: false },
  { img: imgchefs4, price: "15$", name: "Spaghetti Carbonara", state: false },
];
export default {
  data() {
    return {
      imgchefs1,
      imgchefs2,
      imgchefs3,
      imgchefs4,
      countSlider: 0,
      carouselData: 0,
      dataSlideItem,
      hooperSettings: {
        infiniteScroll: true,
        itemsToSlide: 1,
        breakpoints: {
          1024: {
            itemsToShow: 3,
          },
          768: {
            itemsToShow: 3,
          },
          414: {
            itemsToShow: 1,
          },
        },
      },
    };
  },
  watch: {
    carouselData() {
      this.$refs.carousel.slideTo(this.carouselData);
    },
  },
  methods: {
    slideTo(item) {
      this.$refs.carousel.slideTo(item);
    },

    updateCarousel(payload) {
      this.carouselData = payload.currentSlide;
      if (payload.currentSlide === 4) {
        this.carouselData = 0;
      } else if (this.carouselData === -1) {
        this.carouselData = 3;
      }
      console.log(this.carouselData);
      this.dataSlideItem = this.dataSlideItem.map((item, index) => {
        this.carouselDatas = this.carouselData + 1;
        if (this.carouselDatas === 4) {
          this.carouselDatas = 0;
        }
        if (index === this.carouselDatas) {
          return { ...item, state: true };
        }
        return { ...item, state: false };
      });
    },
  },
};
</script>
<style lang="scss" scoped>
@import "~/assets/scss/components/home-pages/chefs.scss";

@keyframes boxShaddow {
  from {
    box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
  }
  to {
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.4);
  }
}
</style>