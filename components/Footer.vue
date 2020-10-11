<template>
  <div class="footer">
    <div class="footer__container">
      <div class="footer__container__top">
        <div class="footer__container__top__infor">
          <div class="footer__container__top__infor__img">
            <img :src="imgLogoHeader" alt="" />
          </div>

          <p>
            Hella narwhal Cosby sweater McSweeney's, salvia kitsch before they
            sold out High Life. Umami tattooed sriracha meggings pickled Marfa
            Blue.
          </p>
        </div>
        <div class="footer__container__top__opening-hours">
          <h3>Opening Hours</h3>
          <div class="footer__container__top__opening-hours__line"></div>
          <ul class="footer__container__top__opening-hours__list">
            <li>Mon ~ Fri: 9 am - 10 pm</li>
            <li>Sat ~ Sun : 9 am - 11 pm</li>
            <li>National day : 11 am - 11 pm</li>
          </ul>
        </div>

        <div class="footer__container__top__nemu">
          <h3>Main Menu</h3>
          <div class="footer__container__top__nemu__line"></div>
          <ul class="footer__container__top__nemu__list">
            <li><a-icon type="right" /> <span>Home</span></li>
            <li><a-icon type="right" /> <span>About us</span></li>
            <li><a-icon type="right" /> <span>Menu</span></li>
            <li><a-icon type="right" /> <span>Blog</span></li>
            <li><a-icon type="right" /> <span>Contact us</span></li>
          </ul>
        </div>
        <div class="footer__container__top__contact">
          <h3>Get in Touch</h3>
          <div class="footer__container__top__contact__line"></div>
          <a-input placeholder="input search text"> </a-input>
          <div class="footer__container__top__contact__link">
            <img :src="imgIcon1" alt="" />
            <img :src="imgIcon2" alt="" />
            <img :src="imgIcon3" alt="" />
            <img :src="imgIcon4" alt="" />
          </div>
        </div>
      </div>
    </div>
    <hr />
    <div class="footer__bottom">
      <div class="footer__bottom__container">
        <p>Fos Restaurant © 2020. All Rights Reserved.</p>
        <div class="footer__bottom__container__content">
          <p>Terms of Service</p>
          <p>Privacy Policy</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import imgLogoHeader from "../assets/img/Logo_White.png";
import imgIcon1 from "../assets/img/icon-1.svg";
import imgIcon2 from "../assets/img/icon-2.svg";
import imgIcon3 from "../assets/img/icon-3.svg";
import imgIcon4 from "../assets/img/icon-4.svg";
export default {
  data: () => {
    return {
      imgLogoHeader,
      imgIcon1,
      imgIcon2,
      imgIcon3,
      imgIcon4,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "~/assets/scss/layout/footer.scss";
.footer {
  background-image: url("../assets/img/Testimonials.png");
}
</style>
