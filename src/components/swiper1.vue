<template>
  <div>
    <div class="swiper-container" id="bannerlist">
      <div class="swiper-wrapper">
        <div class="swiper-slide" v-for="(item, index) in todos" :key="index">
          <div class="slidebg">
            <img :src="item.img" />
            <h1 class="font-hide">{{ item.title }}</h1>
            <p class="morefont">{{ item.text }}</p>
          </div>
        </div>
      </div>
      <div class="flex-center">
        <!-- Add Pagination -->
        <div class="swiper-button-prev"></div>
        <div class="swiper-pagination"></div>
        <!-- Add Navigation -->
        <div class="swiper-button-next"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper from "swiper";
export default {
  name: "Swiper1",
  props: { todos: Array },
  components: {},
  data() {
    return {};
  },
  mounted() {
    var swiper = new Swiper("#bannerlist", {// eslint-disable-line no-unused-vars
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
      },
      slidesPerView: 3, //展示数量
      spaceBetween: 20, //间距
      slidesPerGroup: 3,
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
      loop: true,
      autoplay: {
        delay: 5000,
        stopOnLastSlide: true,
        disableOnInteraction: false,
      },
      observer: true,
      observeParents: true,
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
  img {
    width: 100%;
  }
}

:root {
  --swiper-theme-color: white !important;
}
#bannerlist {
  .slidebg {
    background: #f7f7f7;
    padding: 10px;
    border-radius: 6px;
    text-align: left;
    h1 {
      font-size: 16px;
      line-height: 30px;
      margin: 5px 0;
      color: #5b5b5b;
    }
    p {
      -webkit-line-clamp: 3;
      line-height: 25px;
      font-size: 12px;
      color: #898989;
    }
  }
  .swiper-button-next,
  .swiper-button-prev {
    color: #149b83;
    bottom: 0 !important;
    position: relative;
    margin: 0 30px;
    &::after {
      font-size: 18px;
    }
  }
  .swiper-pagination {
    position: relative;
  }
  .swiper-pagination-bullet {
  opacity: 1;
  background: #149b83;
  opacity: 0.5;
  margin: 0 5px;
}
.swiper-pagination-bullet-active {
  background: #149b83;
  opacity: 1;
}
}
</style>
