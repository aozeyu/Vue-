<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of recommendList" :key="index">
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
  data() {
    return {
      recommendList:[
        {
          id:'0001',
          imgUrl:'https://imgs.qunarzz.com/vs_ceph_vcimg/f03f5ac90ae59d0d9c6332a2bfd9782e.jpeg',
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
.item-img-wrapper
  height 0
  overflow hidden
  padding-bottom 33.9%
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