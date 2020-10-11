<template>
  <div class="reserve">
    <div class="reserve__container">
      <form>
        <div class="reserve__container__title">
          <div class="reserve__container__title__line"></div>
          <p>advanced booking</p>
          <h2>Reserve a table</h2>
        </div>
        <div class="reserve__container__input">
          <div class="reserve__container__input__items">
            <div
              class="reserve__container__input__items__label"
              @click="showHideSelect"
            >
              <label>party size</label>
              <img :src="imgArrowDown" alt="" />
            </div>
            <div class="reserve__container__input__items__item">
              <a-select
                label-in-value
                :default-value="{ key: 'lucy' }"
                @change="handleChange"
                :open="isOpen"
                :showArrow="false"
                :class="reserveClass"
              >
                <a-select-option @click="showHideSelect" value="jack">
                  <a-icon slot="suffixIcon" type="team" />
                  For 4
                </a-select-option>
                <a-select-option @click="showHideSelect" value="lucy">
                  <a-icon slot="suffixIcon" type="team" /> For 5
                </a-select-option>
              </a-select>
            </div>
          </div>

          <!--  -->
          <div class="reserve__container__input__items">
            <div
              class="reserve__container__input__items__label"
              @click="showHideTime"
            >
              <label>Time</label>
              <img :src="imgArrowDown" alt="" />
            </div>
            <div class="reserve__container__input__items__item">
              <a-time-picker :open="isOpetTime" :class="reserveClass">
                <a-button
                  slot="addon"
                  size="small"
                  type="primary"
                  @click="showHideTime"
                >
                  Ok
                </a-button>
              </a-time-picker>
            </div>
          </div>

          <div class="reserve__container__input__items">
            <div
              class="reserve__container__input__items__label"
              @click="showHideDate"
            >
              <label>Date</label>
              <img :src="imgArrowDown" alt="" />
            </div>
            <div class="reserve__container__input__items__item">
              <a-date-picker
                :open="isOpetDate"
                @change="onChange"
                :class="reserveClass"
              />
            </div>
          </div>

          <div class="reserve__container__input__items">
            <div class="reserve__container__input__items__label">
              <label>name</label>
            </div>
            <div class="reserve__container__input__items__item">
              <a-input
                :class="reserveClass"
                placeholder="Your name"
                v-decorator="[
                  'note',
                  {
                    rules: [
                      { required: true, message: 'Please input your note!' },
                    ],
                  },
                ]"
              />
            </div>
          </div>
          <div class="reserve__container__input__items">
            <div class="reserve__container__input__items__label">
              <label>No.phone</label>
            </div>
            <div class="reserve__container__input__items__item">
              <a-input
                :class="reserveClass"
                placeholder="Your phone"
                v-decorator="[
                  'note',
                  {
                    rules: [
                      { required: true, message: 'Please input your note!' },
                    ],
                  },
                ]"
              />
            </div>
          </div>
          <div class="reserve__container__input__items">
            <div class="reserve__container__input__items__label">
              <label>Email</label>
            </div>
            <div class="reserve__container__input__items__item">
              <a-input
                :class="reserveClass"
                placeholder="your@domain.com"
                v-decorator="[
                  'note',
                  {
                    rules: [
                      { required: true, message: 'Please input your note!' },
                    ],
                  },
                ]"
              />
            </div>
          </div>
        </div>
        <div class="reserve__container__btn">
          <button>Check Availability</button>
        </div>
      </form>
      <div class="reserve__container__img"><img :src="imgTabel" alt="" /></div>
    </div>
  </div>
</template>
<script>
import moment from "moment";
import imgArrowDown from "../../../assets/img/arrow-down.png";
import imgTabel from "../../../assets/img/img-table.png";
export default {
  data: () => {
    return {
      imgArrowDown,
      imgTabel,
      isOpen: false,
      isOpetTime: false,
      isOpetDate: false,
      reserveClass: "reserve__container__input__items__item__option",
    };
  },
  methods: {
    showHideSelect() {
      this.isOpen = !this.isOpen;
    },
    showHideTime() {
      this.isOpetTime = !this.isOpetTime;
    },
    showHideDate() {
      this.isOpetDate = !this.isOpetDate;
    },
    handleChange(value) {
      console.log(value); // { key: "lucy", label: "Lucy (101)" }
    },
    onChange(date, dateString) {
      this.isOpetDate = !this.isOpetDate;
      console.log(date, dateString);
    },
  },
};
</script>
<style lang="scss" scoped>
@import "~/assets/scss/components/home-pages/reserve.scss";
</style>