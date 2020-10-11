<template>
  <div class="blog">
    <div class="blog__container">
      <div class="blog__container__title">
        <div class="blog__container__title__line"></div>
        <p>Amazing Blogs</p>
        <h2>Fos’s news</h2>
      </div>
      <div class="blog__container__blog-list">
        <div
          class="blog__container__blog-list__item"
          v-for="(item, index) in dataBlog"
          :key="index"
        >
          <div class="blog__container__blog-list__item__img">
            <div class="blog__container__blog-list__item__img__item">
              <img :src="item.img" alt="" />
            </div>

            <p>
              May <br />
              10
            </p>
          </div>
          <h3>{{ item.title }}</h3>
          <p>
            {{ item.content }}
          </p>
          <div class="blog__container__blog-list__item__btn">
            <button><span>Read More</span> <img src="" alt="" /></button>
          </div>
        </div>
      </div>
      <div class="blog__container__btn">
        <button>View All Menu</button>
      </div>
    </div>
  </div>
</template>

<script>
import imgBlog1 from "../../../assets/img/img-blog-1.png";
import imgBlog2 from "../../../assets/img/img-blog-2.png";
import imgBlog3 from "../../../assets/img/img-blog-3.png";

let dataBlog = [
  {
    img: imgBlog1,
    title: "Banjo tote bag bicycle rights, High Life sartorial",
    content:
      " It was a humorously perilous business for both of us. Before we proceed further that the monkey-rope.",
  },
  {
    img: imgBlog2,
    title: "So strongly and metaphysically did I conceive of my situation",
    content:
      " It was a humorously perilous business for both of us. Before we proceed further that the monkey-rope.",
  },
  {
    img: imgBlog3,
    title: "Portland , YOLO Echo Park",
    content:
      " It was a humorously perilous business for both of us. Before we proceed further that the monkey-rope.",
  },
];
export default {
  data: () => {
    return {
      imgBlog1,
      imgBlog2,
      imgBlog3,
      dataBlog,
    };
  },
};
</script>

<style lang="scss">
@import "~/assets/scss/components/home-pages/blog.scss";
</style>