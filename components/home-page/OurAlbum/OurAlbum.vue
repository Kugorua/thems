<template>
  <div class="our-album">
    <div class="our-album__container">
      <div class="our-album__container__title">
        <div class="blog__container__title__line"></div>
        <p>Our Album</p>
        <h2>Stunning gallery</h2>
      </div>
      <div class="our-album__container__slider">
        <div class="our-album__container__slider__item">
          <div class="our-album__container__slider__item__img">
            <img :src="imgAbum1" alt="" />
            <div class="our-album__container__slider__item__img__hover-1"></div>
            <div class="our-album__container__slider__item__img__hover-2"></div>
            <div class="our-album__container__slider__item__img__hover-3"></div>
            <div class="our-album__container__slider__item__img__hover-4"></div>
          </div>
          <div class="our-album__container__slider__item__img">
            <img :src="imgAbum2" alt="" />
            <div class="our-album__container__slider__item__img__hover-1"></div>
            <div class="our-album__container__slider__item__img__hover-2"></div>
            <div class="our-album__container__slider__item__img__hover-3"></div>
            <div class="our-album__container__slider__item__img__hover-4"></div>
          </div>
        </div>
        <div class="our-album__container__slider__item">
          <div class="our-album__container__slider__item__img">
            <img :src="imgAbum3" alt="" />
            <div class="our-album__container__slider__item__img__hover-1"></div>
            <div class="our-album__container__slider__item__img__hover-2"></div>
            <div class="our-album__container__slider__item__img__hover-3"></div>
            <div class="our-album__container__slider__item__img__hover-4"></div>
          </div>
          <div class="our-album__container__slider__item__img">
            <img :src="imgAbum4" alt="" />
            <div class="our-album__container__slider__item__img__hover-1"></div>
            <div class="our-album__container__slider__item__img__hover-2"></div>
            <div class="our-album__container__slider__item__img__hover-3"></div>
            <div class="our-album__container__slider__item__img__hover-4"></div>
          </div>
        </div>
        <div class="our-album__container__slider__item">
          <div class="our-album__container__slider__item__img">
            <img :src="imgAbum5" alt="" />
            <div class="our-album__container__slider__item__img__hover-1"></div>
            <div class="our-album__container__slider__item__img__hover-2"></div>
            <div class="our-album__container__slider__item__img__hover-3"></div>
            <div class="our-album__container__slider__item__img__hover-4"></div>
          </div>
          <div class="our-album__container__slider__item__img">
            <img :src="imgAbum6" alt="" />
            <div class="our-album__container__slider__item__img__hover-1"></div>
            <div class="our-album__container__slider__item__img__hover-2"></div>
            <div class="our-album__container__slider__item__img__hover-3"></div>
            <div class="our-album__container__slider__item__img__hover-4"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import imgAbum1 from "../../../assets/img/abum-1.png";
import imgAbum2 from "../../../assets/img/abum-2.png";
import imgAbum3 from "../../../assets/img/abum-3.png";
import imgAbum4 from "../../../assets/img/abum-4.png";
import imgAbum5 from "../../../assets/img/abum-5.png";
import imgAbum6 from "../../../assets/img/abum-6.png";
export default {
  data: () => {
    return {
      imgAbum1,
      imgAbum2,
      imgAbum3,
      imgAbum4,
      imgAbum5,
      imgAbum6,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "~/assets/scss/components/home-pages/our-album.scss";
</style>