<template>
  <div>
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <div class="swiper-slide" v-for="(item, index) in items" :key="index"><img :src="item.img"></div>
      </div>
      <!-- Add Pagination -->
      <div class="swiper-pagination"></div>
      <!-- Add Navigation -->
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
    </div>
  </div>
</template>

<script>
import Swiper from "swiper";
export default {
  name: "Swiper",
  props: { items: Array },
  components: {},
  data() {
    return {};
  },
  mounted() {
    var swiper = new Swiper(".swiper-container", {// eslint-disable-line no-unused-vars
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
      },
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
      loop:true,
      autoplay:{
          delay:5000,
          stopOnLastSlide:true,
          disableOnInteraction:false
      }
    });
  },
  created() {},
  methods: {},
};
</script>
<style lang="less">
.swiper-container {
  width: 100%;
  height: 100%;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: #fff;
  /* Center slide text vertically */
  display: -webkit-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  -webkit-align-items: center;
  align-items: center;
  img{
      width: 100%;
  }
}
.swiper-pagination-bullet{
    opacity: 1;
    background: white;
}
.swiper-pagination-bullet-active{
    background: green;
}
:root{
    --swiper-theme-color:white !important;
}
</style>
