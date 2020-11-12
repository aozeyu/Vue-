<template>
  <div class="list" ref="wrapper">
    <div>
    <div class="area">
      <div class="title border-topbottom" >当前城市</div>
      <div class="button-list">
        <div class="button-wrapper">
          <div class="button">株洲</div>
        </div>
      </div>
    </div>
        <div class="area">
      <div class="title border-topbottom" >热门城市</div>
      <div class="button-list">
        <div class="button-wrapper" v-for="(item,index) of hot" :key="index">
          <div class="button">{{item.name}}</div>
        </div>
      </div>
    </div>
    <div class="area" v-for="(item,key) of cities" :key="key">
      <div class="title border-topbottom" >A</div>
      <div class="item-list">
        <div class="item border-bottom" v-for="(innerItem,index) of item" :key="index">
          {{innerItem.name}} 
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
import BetterScroll from 'better-scroll'
export default {
  name: "CityList",
  props:{
    cities:Object,
    hot:Array //hot只是父组件传过来的代表着hotCites的别名而已
  },
  mounted() {
    this.scroll = new BetterScroll(this.$refs.wrapper) //this.$refs.wrapper代表获取到的dom元素
  },
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .title
      line-height: .54rem
      background: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .button-list
      overflow: hidden
      padding: .1rem .6rem .1rem .1rem
      .button-wrapper
        float: left
        width: 33.33%
        .button
          margin: .1rem
          padding: .1rem 0
          text-align: center
          border: .02rem solid #ccc
          border-radius: .06rem
    .item-list
      .item
        line-height: .76rem
        padding-left: .2rem    
</style>