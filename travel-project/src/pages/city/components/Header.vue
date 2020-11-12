<template>
  <div class="header">城市选择
    <router-link to="/">
    <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "CityHeader", //导出City组件
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header 
  height: $headerHeight;
  line-height: $headerHeight;
  text-align: center;
  color: #fff;
  background: $bgColor;
  font-size: 0.32rem;
  position relative
  .header-back
    position absolute
    top 0
    left 0 //相对已定位的父元素进行定位
    width .64rem
    text-align center
    font-size .4rem
    color #fff
</style>