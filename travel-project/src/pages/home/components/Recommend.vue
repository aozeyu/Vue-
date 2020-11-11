<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of recommendList" :key="index">
          <img :src="item.imgUrl" alt="" class="item-img" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  data() {
    return {
      recommendList:[
        {
          id:'0001',
          imgUrl:'//img1.qunarzz.com/sight/p0/1507/45/b74377c618d5306b709ceaf859f8f507.water.jpg_256x160_78e0a6a5.jpg',
          title:'大连圣亚海洋世界',
          desc:'浪漫大连首站,浪漫的海洋主题乐园'
        }
      ]
    }
  },
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';
.title 
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
  margin-top: 0.2rem;
.item
  display flex
  height 1.9rem
  overflow hidden
  .item-img 
    width 1.7rem
    height 1.7rem
    padding .1rem
  .item-info
    flex 1 //撑开剩余的宽度
    padding .1rem
    min-width 0
    .item-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .item-desc
      line-height .4rem
      color #ccc
      ellipsis()
    .item-button
      line-height .44rem
      margin-top .16rem
      background #ff9300
      padding 0 .2rem
      border-radius .06rem
      color #fff
</style>