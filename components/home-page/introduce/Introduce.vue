<template>
  <div class="introduce" ref="intor">
    <div class="introduce__container">
      <div
        class="introduce__container__item"
        :class="{ introduce__container__scroll: isCroll }"
        v-for="(item, index) in dataIntroduce"
        :key="index"
      >
        <div class="introduce__container__item__icon">
          <div class="introduce__container__item__icon__wrap">
            <div class="introduce__container__item__icon__wrap__img"></div>
          </div>
          <div class="introduce__container__item__icon__img">
            <img :src="item.img" alt="" />
          </div>
        </div>

        <div class="introduce__container__item__infor">
          <span class="introduce__container__item__infor__number">{{
            item.number
          }}</span>
          <span class="introduce__container__item__infor__text">
            {{ item.text }}</span
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import imgIconCheer from "../../../assets/img/icon-cheer.png";
import imgIconDish from "../../../assets/img/icon-dish.png";
import imgIconMedal from "../../../assets/img/icon-medal.png";
import imgIconChef from "../../../assets/img/icon-chef-hat.png";
let dataIntroduce = [
  {
    img: imgIconCheer,
    numberSt: "04",
    number: 0,
    numberMax: 4,
    text: "number of restaurant",
    id: 0,
  },
  {
    img: imgIconDish,
    numberSt: "68",
    number: 0,
    numberMax: 68,
    text: "new food menu dishes",
    id: 1,
  },
  {
    img: imgIconMedal,
    numberSt: "10",
    number: 0,
    numberMax: 10,
    text: "years of experience",
    id: 2,
  },
  {
    img: imgIconChef,
    numberSt: "14",
    number: 0,
    numberMax: 14,
    text: "new chef in kitchen",
    id: 3,
  },
];
export default {
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  data: () => {
    return { dataIntroduce, isCroll: false, numberScroll: 0 };
  },
  methods: {
    handleScroll() {
      if (window.top.scrollY >= Number(this.$refs.intor.offsetTop) - 335) {
        this.isCroll = true;
        this.numberScroll = this.numberScroll + 1;

        if (this.numberScroll === 1) {
          for (let item of this.dataIntroduce) {
            for (let i = 1; i <= item.numberMax; i++) {
              ((index) => {
                setTimeout(() => {
                  this.dataIntroduce[item.id].number = index;
                }, index * 50 + 500);
              })(i);
            }
          }
        }
      }
    },
  },
};
</script>

<style lang="scss">
@import "~/assets/scss/components/home-pages/introduce.scss";
</style>