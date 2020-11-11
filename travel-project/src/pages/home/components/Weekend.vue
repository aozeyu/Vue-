<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of list" :key="index">
          <div class="item-img-wrapper">
            <img :src="item.imgUrl" alt="" class="item-img" />
          </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  props:{
    list:Array //从父组件接受到的数组
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';
.title 
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
.item-img-wrapper
  height 0
  overflow hidden
  padding-bottom 37.09%
  .item-img 
    width 100% //宽度在weekend组件内不再定死
  .item-info
    padding .1rem
    .item-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .item-desc
      line-height .4rem
      color #ccc
      ellipsis()
</style>