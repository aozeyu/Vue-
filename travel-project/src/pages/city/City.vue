<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
    <city-alphabet></city-alphabet>
  </div>
</template>

<script>
import CityHeader from "./components/Header";
import CitySearch from "./components/Search";
import CityList from "./components/List";
import CityAlphabet from "./components/Alphabet";
export default {
  name: "City", //导出City组件
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet //别忘了注册组件
  },
};
</script>

<style lang="stylus" scoped>

</style>