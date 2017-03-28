<template>
  <div >
    <v-header :seller="seller"></v-header>
    <div class="tab">
    <!-- <router-link> 默认会被渲染成一个 `<a>` 标签 -->
    <router-link to="/goods" class="tab-item">商品</router-link>
    <router-link to="/ratings" class="tab-item">评价</router-link>
    <router-link to="/seller" class="tab-item">商家</router-link>
    </div>
    <!-- 路由出口 -->
    <!-- 路由匹配到的组件将渲染在这里 -->
    <router-view></router-view>
  </div>
</template>

<script type="text/ecmascript-6">
  import header from 'components/header/header';
  const ERR_OK = 0;

export default {

  data() {
      return {
         seller: {}
      };
  },
  created() {
    // 虽然报错，不过编译通过，可能是webstrom的问题。
    this.$http.get('/api/seller').then((response) => {
      response = response.body;
      if (response.errno === ERR_OK) {
        this.seller = response.data;
        console.log(this.seller);
      }
    });
  },
  components: {
    'v-header': header
  }
};
</script>


<style lang="stylus" rel="stylesheet/stylus">
  @import "common/stylus/appvue.styl";
</style>
