<template>
  <div class="home">
    <Banner />
    <Introduce />
    <Discover />
    <DishOfDay />
    <CustomerStore />
    <Chefs />
    <Reserve />
    <Blog />
    <OurAlbum />
  </div>
</template>

<script>
import Banner from "../components/home-page/Banner/Banner";
import Introduce from "../components/home-page/introduce/Introduce";
import Discover from "../components/home-page/Discover/Discover";
import DishOfDay from "../components/home-page/DishOfDay/DishOfDay";
import CustomerStore from "../components/home-page/CustomerStore/CustomerStore";
import Chefs from "../components/home-page/Chefs/Chefs";
import Reserve from "../components/home-page/Reserve/Reserve";
import Blog from "../components/home-page/blog/Blog";
import OurAlbum from "../components/home-page/OurAlbum/OurAlbum";
export default {
  head: {
    title: "Home Page",
  },
};
</script>

<style lang="scss" scoped></style>
