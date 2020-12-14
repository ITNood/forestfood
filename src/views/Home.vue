<template>
  <div style="background: #f7f7f7">
    <Navbar />
    <Swiper :items="banner" />
    <div class="container">
      <!--content one-->
      <div class="content clear">
        <div class="content_left left">
          <!--森林食品概况-->
          <div class="food_new">
            <div class="flex-center title">
              <i class="icon iconfont icon-fuwugaikuang"></i>森林食品概况
            </div>
            <div class="survey">
              <!--什么是食品 start-->
              <div class="whatfood flex-center">
                <div class="whatfood_content">
                  <h1>什么是森林食品?</h1>
                  <p class="morefont">
                    作为大自然对人类的馈赠，森林食品以森林生态环境下生长动植物和微生物为原料，遵循动植物和微生物自然生长规律生产加工，并遵循可持续经营的原则，无人工合成添加物，具有原生态、无污染、健康、安全等特性的各类可食用的林产品。
                  </p>
                </div>
                <img src="../static/images/food1.png" />
              </div>
              <!--什么是食品 end-->
              <!--森林食品分类 start-->
              <div class="foodClass">
                <h1>森林食品分类</h1>
                <ul class="foodlist flex-center">
                  <li
                    v-for="(item, index) in items"
                    :key="index"
                    class="flex-1"
                  >
                    <img :src="item.img" />
                    <h1>{{ item.name }}</h1>
                    <p class="font-hide">{{ item.text }}</p>
                  </li>
                </ul>
              </div>
              <!--森林食品分类 end-->
              <!--食品安全架构 start-->
              <div class="foodClass" style="border-bottom: none">
                <h1>食品安全架构</h1>
                <ul class="foodlist flex-center">
                  <img src="../static/images/safe.png" style="width: 100%" />
                </ul>
              </div>
              <!--食品安全架构 end-->
            </div>
          </div>
          <!--森林食品概况 end-->

          <!--认证概况 start-->
          <div class="food_new" style="margin-top: 30px">
            <div class="flex-center title">
              <i
                class="icon iconfont icon-icon_zhinan"
                style="font-size: 30px"
              ></i
              >认证概况
            </div>
            <div class="survey">
              <!--上 start-->
              <div class="attesttion flex">
                <ul class="attest_left">
                  <li v-for="(item, index) in list" :key="index">
                    <router-link to="">
                      <h1 class="font-hide">{{ item.title }}</h1>
                      <p class="morefont">{{ item.text }}</p>
                    </router-link>
                  </li>
                </ul>
                <div class="attest_img relative flex-center">
                  <img src="../static/images/attest.png" />
                  <p class="font-hide">保护耕地 重视轮作 培养接班人</p>
                </div>
              </div>
              <!--上 end-->

              <!--下 start-->
              <div class="attesttion_content flex">
                <div
                  class="attesttion_lsit flex-1"
                  v-for="(test, index) in tests"
                  :key="index"
                >
                  <h1>{{ test.title }}</h1>
                  <ul class="content_list">
                    <li v-for="content in test.contents" :key="content.id">
                      <router-link
                        :to="{ path: '/', query: { id: content.id } }"
                        class="font-hide"
                        >{{ content.text }}</router-link
                      >
                    </li>
                  </ul>
                </div>
              </div>
              <!--下 end-->
            </div>
          </div>
          <!--认证概况 end-->
        </div>
        <div class="content_right right">
          <!--最新公告 start-->
          <div class="notice">
            <div class="flex-center title">
              <i class="icon iconfont icon-gonggao"></i>最新公告
            </div>
            <ul class="newslist">
              <li v-for="notice in notices" :key="notice.id">
                <router-link
                  :to="{ path: '/', query: { id: notice.id } }"
                  class="font-hide"
                  >{{ notice.text }}</router-link
                >
              </li>
            </ul>
          </div>
          <!--最新公告 end-->
          <!--证书文件 start-->
          <div class="file">
            <div class="flex-center title">
              <i class="icon iconfont icon-gonggao"></i>证书文件
            </div>
            <div class="download">
              <a
                v-for="(load, index) in download"
                :key="index"
                :href="load.url"
                class="relative font-hide"
                >{{ load.title }}<i class="el-icon-download"></i
              ></a>
            </div>
          </div>
          <!--证书文件 end-->

          <!--认证指南 start-->
          <div class="guide">
            <div class="flex-center title">
              <i class="icon iconfont icon-gonggao"></i>认证指南
            </div>
            <ul class="guidelist clear">
              <li v-for="(guide, index) in guides" :key="index">
                <img :src="guide.img" />
                <h5>{{ guide.name }}</h5>
              </li>
            </ul>
          </div>
          <!--认证指南 end-->
          <!--申请认证- start-->
          <div class="apply">
            <div class="flex-center title">
              <i class="icon iconfont icon-gonggao"></i>申请认证
            </div>
            <div class="applycontent">
              <p>
                企业可根据中国森林食品认证结果和产能，进行报备申请中国森林食品认证赋码标，获取中国森林食品认证证书
              </p>
              <el-button class="more" @click="more">了解详情</el-button>
            </div>
          </div>
          <!--申请认证 end-->
        </div>
      </div>
      <!--content one end-->

      <!--企业认证  start-->
      <div class="business clear">
        <!--left -->
        <div class="content_left left">
          <div class="businesscontent">
            <div class="flex-center title">
              <i class="icon iconfont icon-gonggao"></i>认证企业
            </div>

            <div class="business_img">
                <Swiper1 :todos="listbaner"/>
            </div>
          </div>
        </div>
        <!--right-->
        <div class="content_right right">
          <!--认证企业查询-->
          <router-link to="" class="businessSearch flex-center">
            <i class="icon iconfont icon-gonggao"></i>认证企业查询
          </router-link>
          <!--打假平台-->
          <div class="crack">
            <div class="flex-center title">
              <i class="icon iconfont icon-shiwu-chuizi"></i>打假平台
            </div>
            <div class="crackContent">
              <p>森林食品认证赋码标具有一品一标，一标一码特性，是唯一加密追溯的认证体系。如果发现了假冒森林食品，可以向认证机构进行投诉。</p>
              <el-button @click="handlCrack" class="exposure">打假曝光</el-button>
            </div>
          </div>
        </div>
      </div>
      <!--企业认证  end-->

      <!--森林食品商城 start-->
      <div class="mall">
        <div class="flex-center title">
              <i class="icon iconfont icon-gouwuche"></i>森林食品商城
        </div>
      </div>
      <!--森林食品商城 end-->
    </div>
    <Footer />
  </div>
</template>

<script>
import Footer from "../components/footer";
import Navbar from "../components/nav";
const Swiper=()=>import('@/components/swiper')
const Swiper1 =()=>import('@/components/swiper1')
export default {
  components: { Navbar, Footer, Swiper,Swiper1 },
  data() {
    return {
      banner: [
        { img: require("../static/images/banner1.jpg") },
        { img: require("../static/images/banner2.jpg") },
        { img: require("../static/images/banner3.jpg") },
      ],
      listbaner:[
          {img:require('../static/images/logolist.png'),title:'始终不渝 固守正道',text:'永贞堂股份有限公司是一家在香港注册和运营，以中医药为核心，发展大健康产业的多元化控股企业集团。'},
          {img:require('../static/images/logolist.png'),title:'始终不渝 固守正道',text:'永贞堂股份有限公司是一家在香港注册和运营，以中医药为核心，发展大健康产业的多元化控股企业集团。'},
          {img:require('../static/images/logolist.png'),title:'始终不渝 固守正道',text:'永贞堂股份有限公司是一家在香港注册和运营，以中医药为核心，发展大健康产业的多元化控股企业集团。'},
          {img:require('../static/images/logolist.png'),title:'始终不渝 固守正道',text:'永贞堂股份有限公司是一家在香港注册和运营，以中医药为核心，发展大健康产业的多元化控股企业集团。'},
          {img:require('../static/images/logolist.png'),title:'始终不渝 固守正道',text:'永贞堂股份有限公司是一家在香港注册和运营，以中医药为核心，发展大健康产业的多元化控股企业集团。'},
          {img:require('../static/images/logolist.png'),title:'始终不渝 固守正道',text:'永贞堂股份有限公司是一家在香港注册和运营，以中医药为核心，发展大健康产业的多元化控股企业集团。'},
      ],
      items: [
        {
          img: require("../static/images/foodclass1.png"),
          name: "生鲜品",
          text: "蔬菜、粮食、水果、肉类、蛋类",
        },
        {
          img: require("../static/images/foodclass1.png"),
          name: "生鲜品",
          text: "蔬菜、粮食、水果、肉类、蛋类",
        },
        {
          img: require("../static/images/foodclass1.png"),
          name: "生鲜品",
          text: "蔬菜、粮食、水果、肉类、蛋类",
        },
      ],
      list: [
        {
          title: "中国森林食品认证管理办法",
          text:
            "中国林业生态发展促进会依据民政部核准的业务范围，经常务理事会研究决定，在全国范围内开展",
        },
        {
          title: "中国森林食品认证管理办法",
          text:
            "中国林业生态发展促进会依据民政部核准的业务范围，经常务理事会研究决定，在全国范围内开展",
        },
        {
          title: "中国森林食品认证管理办法",
          text:
            "中国林业生态发展促进会依据民政部核准的业务范围，经常务理事会研究决定，在全国范围内开展",
        },
      ],
      tests: [
        {
          title: "业内报道",
          contents: [
            { text: "中国森林食品交易博览会在上海举办", id: 1 },
            { text: "中国森林食品交易博览会在上海举办", id: 2 },
            { text: "中国森林食品交易博览会在上海举办", id: 7 },
            { text: "中国森林食品交易博览会在上海举办", id: 9 },
          ],
        },
        {
          title: "行业动态",
          contents: [
            { text: "中国森林食品交易博览会在上海举办", id: 1 },
            { text: "中国森林食品交易博览会在上海举办", id: 21 },
            { text: "中国森林食品交易博览会在上海举办", id: 3 },
            { text: "中国森林食品交易博览会在上海举办", id: 4 },
          ],
        },
      ],
      notices: [
        { text: "中国森林食品交易博览会在上海举办", id: 1 },
        { text: "中国森林食品交易博览会在上海举办", id: 2 },
        { text: "中国森林食品交易博览会在上海举办", id: 3 },
        { text: "中国森林食品交易博览会在上海举办", id: 8 },
        { text: "中国森林食品交易博览会在上海举办", id: 7 },
        { text: "中国森林食品交易博览会在上海举办", id: 5 },
      ],
      download: [
        { url: "", title: " 森林食品认证程序 " },
        { url: "", title: " 森林食品认证程序 " },
        { url: "", title: " 森林食品认证程序 " },
        { url: "", title: " 森林食品认证程序 " },
        { url: "", title: " 森林食品认证程序 " },
      ],
      guides: [
        { img: require("../static/images/guide1.png"), name: "1.申请认证" },
        { img: require("../static/images/guide2.png"), name: "2.文件审核" },
        { img: require("../static/images/guide3.png"), name: "3.检测报告" },
        { img: require("../static/images/guide4.png"), name: "4.审核评定" },
        { img: require("../static/images/guide5.png"), name: "5.授予证书" },
        { img: require("../static/images/guide6.png"), name: "6.授予赋码" },
      ],
    };
  },
  created() {

  },
  methods: {
    more() {},
    handlCrack(){}
  },
};
</script>
<style scoped></style>
