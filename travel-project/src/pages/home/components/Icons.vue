<template>
  <div class="icons">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="(item,index) of page" :key="index">
          <div class="icon-img">
            <img
              class="icon-img-content"
              :src="item.imgUrl"
              alt=""
            />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeIcons",
  props:{
    list:Array
  },
  data() {
    return {
      swiperOptions:{
        autoplay:false
      }
    }
  },
  computed: {
    pages(){
      const pages=[]
      this.list.forEach((item,index)=>{
        const page = Math.floor(index/8) //遍历iconList下的每一个数据,用索引除以8计算应该放到第几个页面上前8个item都放到第一个页面上
        if(!pages[page]){
          pages[page]=[]
        }
        pages[page].push(item)
      })
      return pages //将pages数组进行返回
    }
  },
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';
.icons >>> .swiper-container
  height 0
  padding-bottom 50%
.icons
  margin-top .1rem  
 .icon 
    height: 0; // 高度由子元素撑开
    width: 25%;
    float: left;
    overflow: hidden;
    padding-bottom: 25%; // 宽高都是25%
    position: relative;
    .icon-img 
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.1rem;
      .icon-img-content 
        height: 100%;
        display: block; // 变成块级元素
        margin: 0 auto;
    .icon-desc 
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      line-height: 0.44rem;
      height: 0.44rem;
      color: $darkTextColor;
      text-align: center;
      ellipsis()
</style>