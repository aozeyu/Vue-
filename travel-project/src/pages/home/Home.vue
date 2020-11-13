<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
import {mapState} from 'vuex'
export default {
  name: "Home",
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  mounted() {
    this.lastCity = this.city //将当前城市保存下来
    this.getHomeInfo()
  },
  data() {
    return {
      lastCity:'',
      swiperList:[],
      iconList:[],
      recommendList:[],
      weekendList:[]
    } //这些数据都从父组件传给子组件
  },
  computed:{
    ...mapState(['city'])
  },
  activated() {
    if (this.lastCity !== this.city){
      this.lastCity = this.city //更新城市
      this.getHomeInfo()
    }
  },
  methods: {
    getHomeInfo(){
      axios.get('/api/index.json?city='+this.city).then(this.getHomeInfoSucc) //成功后用then回调
    },
    getHomeInfoSucc(res){
      res=res.data
      if(res.ret&&res.data){
        const data=res.data
        this.swiperList=data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      } //这一步是从后台获取的数据给这个父组件
    }
  },
};
</script>

<style>
</style>
