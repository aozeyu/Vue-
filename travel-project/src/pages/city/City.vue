<template>
  <div>
    <city-header></city-header>
    <city-search :cities='cities'></city-search>
    <city-list :cities="cities" :hot="hotCities" :letter="letter"></city-list>
    <city-alphabet :cities="cities" @change="handleLetterChange"></city-alphabet>
  </div>
</template>

<script>
import CityHeader from "./components/Header";
import CitySearch from "./components/Search";
import CityList from "./components/List";
import CityAlphabet from "./components/Alphabet";
import axios from 'axios'
export default {
  name: "City", //导出City组件
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet //别忘了注册组件
  },
  data() {
    return {
      cities: {

      },
      hotCities:[],
      letter: ''
    }
  },
  methods: {
    getCityInfo(){
      axios.get('/api/city.json').then(this.handleGetCityInfoSucc) //成功后调用回调函数
    },
    handleGetCityInfoSucc(res){
      res=res.data //有二层data真正拿到数据看到res.data下面有一个ret的属性进行判断
      if(res.ret && res.data){
        const data = res.data //数据
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterChange(letter){
      this.letter=letter
    }
  },
  mounted() {
    this.getCityInfo() //一旦页面渲染完dom结构立马出发mouted函数
  },
};
</script>

<style lang="stylus" scoped>

</style>
