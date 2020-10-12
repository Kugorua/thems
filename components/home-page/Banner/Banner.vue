<template>
  <div class="banner-slider">
    <ul class="banner-slider__dots">
      <li
        v-for="(item, index) in listSlider"
        :key="index"
        class="banner-slider__dots__item"
        :class="{ 'banner-slider__dots__active': item }"
        @click.prevent="slideTo(index)"
      >
        <span></span>
      </li>
    </ul>
    <hooper
      style="height: 100vh; outline: none"
      ref="carousel"
      @slide="updateCarousel"
      :settings="hooperSettings"
    >
      <slide v-for="(item, index) in listSlider" :key="index">
        <div class="banner">
          <div class="banner__clip-path1">
            <img :src="imgRectangle1" alt="" />
          </div>
          <div class="banner__clip-path2">
            <img :src="imgRectangle2" alt="" />
          </div>
          <div class="banner__container">
            <div class="banner__container__introduce">
              <div class="banner__container__introduce__infor">
                <h2>A Perfect Tasty That Makes Your Dream</h2>
                <p>
                  Hella narwhal Cosby sweater McSweeney's, mami tattooed
                  sriracha meggings pickled Marfa Blue Bottle High Life.
                </p>
                <button>Discover Menu</button>
              </div>
              <div class="banner__container__introduce__contact">
                <div class="banner__container__introduce__contact__item">
                  <img :src="imgPhone" alt="" /> <span>+1 (202) 455-9999</span>
                </div>
                <div class="banner__container__introduce__contact__item">
                  <img :src="imgMail" alt="" /> <span>contact@fos.com</span>
                </div>
              </div>
            </div>
            <div class="banner__container__img">
              <img :src="imgFoot" alt="" />
            </div>
          </div>
        </div>
      </slide>
    </hooper>
  </div>
</template>

<script>

import imgFoot from "../../../assets/img/foot.png";
import imgPhone from "../../../assets/img/icon-phone.png";
import imgMail from "../../../assets/img/icon-mail.png";
import imgRectangle1 from "../../../assets/img/Rectangle.png";
import imgRectangle2 from "../../../assets/img/Rectangle2.png";
export default {
  name: "banner",
  data: () => {
    return {
      imgFoot,
      imgPhone,
      imgMail,
      imgRectangle1,
      imgRectangle2,
      listSlider: [true, false, false, false],
      hooperSettings: {
        infiniteScroll: true,
        itemsToSlide: 1,
        centerMode: true,
        wheelControl: false,
        // autoPlay: true,
        hoverPause: false,
        playSpeed: 10000,
        transition: 400,
        vertical: true,
      },
    };
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

      this.listSlider = this.listSlider.map((item, index) => {
        if (index === this.carouselData) {
          return (item = true);
        }
        return (item = false);
      });
    },
  },
};
</script>

<style lang="scss">
@import "~/assets/scss/components/home-pages/banner.scss";
</style>