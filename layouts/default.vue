<template>
  <div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>
<script>
import Header from "../components/Header";
import Footer from "../components/Footer";
export default {
  data: () => {
    return {
      Header,
      Footer,
    };
  },
};
</script>
<style lang="scss" scoped>

</style>
