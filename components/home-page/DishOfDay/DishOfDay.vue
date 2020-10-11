<template>
  <div class="dish">
    <div class="dish__container">
      <div class="dish__container__title">
        <div class="dish__container__title__line"></div>
        <p>awesome menu</p>
        <h2>Dish of the day</h2>
      </div>
      <div class="dish__container__slider">
        <ul class="dish__container__slider__dots">
          <li
            class="dish__container__slider__dots__item"
            :class="{
              'dish__container__slider__dots__item-active':
                dataSlideItem[0].state,
            }"
            @click.prevent="slideTo(1)"
          >
            <span></span>
          </li>
          <li
            class="dish__container__slider__dots__item"
            @click.prevent="slideTo(3)"
            :class="{
              'dish__container__slider__dots__item-active':
                dataSlideItem[2].state,
            }"
          >
            <span></span>
          </li>
          <li
            class="dish__container__slider__dots__item"
            @click.prevent="slideTo(2)"
            :class="{
              'dish__container__slider__dots__item-active':
                dataSlideItem[1].state,
            }"
          >
            <span></span>
          </li>
        </ul>
        <hooper
          ref="carousel"
          :settings="hooperSettings"
          style="height: 350px; outline: none"
          @slide="updateCarousel"
        >
          <slide class="slider">
            <div class="slider__items">
              <div
                class="slider__container"
                :class="{ 'active-dish': dataSlideItem[1].state }"
              >
                <img :src="imgDish1" alt="" />
                <div class="slider__container__item">
                  <p class="slider__container__item__price">$15</p>
                  <!-- 1 -->
                  <p class="slider__container__item__name">Betroot Salad</p>
                </div>
              </div>
            </div>
          </slide>
          <slide class="slider">
            <div class="slider__items">
              <div
                class="slider__container"
                :class="{ 'active-dish': dataSlideItem[2].state }"
              >
                <img :src="imgDish2" alt="" />
                <div class="slider__container__item">
                  <p class="slider__container__item__price">$25</p>
                  <!-- 1 -->
                  <p class="slider__container__item__name">
                    Spaghetti Carbonara
                  </p>
                </div>
              </div>
            </div>
          </slide>

          <slide class="slider">
            <div class="slider__items">
              <div
                class="slider__container"
                :class="{ 'active-dish': dataSlideItem[0].state }"
              >
                <img :src="imgDish3" alt="" />
                <div class="slider__container__item">
                  <p class="slider__container__item__price">$35</p>
                  <!-- 2 -->
                  <p class="slider__container__item__name">
                    Autumn Pumpkin Soup
                  </p>
                </div>
              </div>
            </div>
          </slide>
        </hooper>
      </div>
      <div class="dish__container__btn">
        <button>View All Menu</button>
      </div>
    </div>
  </div>
</template>

<script>

import imgDish1 from "../../../assets/img/dish-1.png";
import imgDish2 from "../../../assets/img/dish-2.png";
import imgDish3 from "../../../assets/img/dish-3.png";
let dataSlideItem = [
  { img: imgDish1, price: "25$", name: "Spaghetti Carbonara", state: false },
  { img: imgDish2, price: "45$", name: "Spaghetti Carbonara", state: true },
  { img: imgDish3, price: "35$", name: "Spaghetti Carbonara", state: false },
];
export default {
 
  data() {
    return {
      imgDish1,
      imgDish2,
      imgDish3,
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
    slidePrev() {
      this.$refs.carousel.slidePrev();
    },
    slideNext() {
      this.$refs.carousel.slideNext();
    },
    updateCarousel(payload) {
      this.carouselData = payload.currentSlide;

      if (payload.currentSlide === 0) {
        this.carouselData = 3;
      } else if (this.carouselData === -1) {
        this.carouselData = 2;
      }
      this.dataSlideItem = this.dataSlideItem.map((item, index) => {
        if (index === this.carouselData - 1) {
          return { ...item, state: true };
        }
        return { ...item, state: false };
      });
    },
  },
};
</script>
<style lang="scss" scoped>
@import "~/assets/scss/components/home-pages/dish.scss";

@keyframes boxShaddow {
  from {
    box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
  }
  to {
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.4);
  }
}
</style>