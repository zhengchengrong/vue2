<template>
  <div >
    <v-header></v-header>
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

export default {
  name: 'app',
  components: {
    'v-header': header
  }
};
</script>


<style lang="stylus" rel="stylesheet/stylus">
  @import "common/stylus/appvue.styl";
</style>
