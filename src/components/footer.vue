<template>
  <div>
      <div class="footer">
          <div class="container">
              <div class="flex-center unitname">
                  <router-link v-for="(item,index) in items" :key="index" :to="item.url">{{item.name}}</router-link>
              </div>
              <div class="flex-center unitname">
                  <router-link v-for="(item,index) in lists" :key="index" :to="item.url">{{item.name}}</router-link>
              </div>
              <div class="copy">
                  <p>电话: 4009696588    地址: 深圳市福田区福中三路诺德金融中心33楼BC</p>
                  <p>中国林业生态发展促进会 主管    中林森林食品有限公司  主办</p>
                  <p>粤ICP备18022387号-1</p>
              </div>
              <div class="food_logo"><img src="../static/images/food_logo.png"></div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  components: {},
  name:'Footer',
  data() {
    return {
        items:[
            {url:'',name:'中华人民共和国自然资源部'},
            {url:'',name:'中华人民共和国工业和信息化部'},
            {url:'',name:'中华人民共和国民政部'},
            {url:'',name:'国家市场监督管理总局'},
        ],
        lists:[
            {url:'',name:'中华人民共和国农业农村部'},
            {url:'',name:'中华人民共和国水利部'},
            {url:'',name:'中华人民共和国生态环境部'},
            {url:'',name:'中国林业生态发展促进会'},
            {url:'',name:'生态中国'},
        ]
    };
  },
  created() {},
  methods: {},
};
</script>
<style scoped></style>
