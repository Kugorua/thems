<template>
  <div class="discover" ref="discover">
    <div class="discover__container">
      <img
        class="discover__container__img"
        :class="{ 'discover__container__show-img': isCroll }"
        :src="imgBanan"
        alt=""
      />
      <div
        class="discover__container__infor"
        :class="{ 'discover__container__show-infor': isCroll }"
      >
        <div class="discover__container__infor__line"></div>
        <h3>Welcome</h3>
        <h2>Discover Fos’s story</h2>
        <p>
          Fixie tote bag ethnic keytar. Neutra vinyl American Apparel kale chips
          tofu art party, cardigan raw denim quinoa. Craye for paleo tattooed,
          Truffaut skateboard street jean shorts Shoreditch farm-to-table.
        </p>
        <div class="discover__container__infor__btn">
          <button>About us</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import imgBanan from "../../../assets/img/ban-an.png";
export default {
  name: "discover",
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  data: () => {
    return {
      imgBanan,
      isCroll: false,
      numberScroll: 0,
    };
  },
  methods: {
    handleScroll() {
      if (window.top.scrollY >= Number(this.$refs.discover.offsetTop) - 335) {
        this.isCroll = true;
      }
    },
  },
};
</script>

<style lang="scss">
@import "~/assets/scss/components/home-pages/discover.scss";
</style>