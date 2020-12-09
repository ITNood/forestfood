<template>
  <div>
    <div class="nav">
      <div class="container clear">
        <router-link to="/" class="logo left"
          ><img src="../static/images/logo.png"
        /></router-link>
        <div class="flex-center right navlist">
          <router-link v-for="(item, index) in items" :key="index" :to="item.url" avtive-class="active" class="relative">{{
            item.name
          }}</router-link>
          <el-input v-model="value" class="flex-1 search" placeholder="输入关键词搜索" prefix-icon="el-icon-search"></el-input>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  name: "Navbar",
  data() {
    return {
      value: "",
      items: [
    { name: "首页", url: "/" },
        { name: "森林食品认证", url: "/food" },
        { name: "森林食品商城", url: "/mall" },
        { name: "行业新闻", url: "/news" },
        { name: "关于我们", url: "/about" },
      ],
    };
  },
  created() {},
  methods: {},
};
</script>
<style>
.el-input.is-active .el-input__inner, .el-input__inner:focus{
    border-color: #0A6146;
}
</style>
