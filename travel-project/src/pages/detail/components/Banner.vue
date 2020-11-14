<template>
    <div><div class="banner" @click="handleBannerClick">
      <img  class="banner-img" src="http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">美丽的风景世界(AAAAA景区)</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe692;</span>39</div>
      </div>
    </div>
    <common-gallary :img = 'imgs' v-show="showGallary" @close="handleGrallaryClose"></common-gallary>
    </div>
</template>

<script>
  import CommonGallary from 'common/gallary/Gallary'
    export default {
        name: "DetailBanner",
      data(){
        return{
          imgs:[],
          showGallary:false
        }
      },
      components:{
        CommonGallary
      },
      methods:{
        handleBannerClick(){
          this.showGallary = true
        },
        handleGrallaryClose(){
          this.showGallary = false
        }
      }
    }
</script>

<style scoped lang="stylus">
.banner
  position relative
  overflow hidden
  height 0
  padding-bottom 55%
  .banner-img
    width 100%
  .banner-info
    position absolute
    left 0
    right 0
    bottom 0
    line-height .6rem
    display flex
    color #ffffff
    background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
    .banner-title
      font-size .32rem
      padding 0 .2rem

      flex 1
    .banner-number
      margin-top .14rem
      padding 0 .4rem
      line-height .4rem
      height .32rem
      border-radius .2rem
      font-size .24rem
      background rgba(0,0,0,.8)
      .banner-icon
        font-size .24rem

</style>
