<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to='/city'>
    <div class="header-right">
      {{ this.city }}
      <span class="iconfont arow-icon">&#xe64a;</span>
    </div>
    </router-link>
  </div>
</template>

<script>
  import{mapState} from 'vuex'
export default {
  name: "HomeHeader",
  computed:{
    ...mapState(['city'])//将this.$store.state.city映射到city中
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  display: flex;
  line-height:$headerHeight;
  background: $bgColor;
  color: #fff;

  .header-left {
    width: 0.64rem;
    float: left;

    .back-icon {
      text-align: center;
      font-size: 0.4rem;
    }
  }

  .header-input {
    flex: 1; // 剩余空间自动撑开
    background: #fff;
    margin-top: 0.12rem;
    height: 0.64rem;
    line-height: 0.64rem;
    margin-left: 0.2rem;
    border-radius: 0.1rem;
    color: #ccc;
    padding-left: 0.2rem;
  }

  .header-right {
    min-width: 1.04rem;
    padding 0 .1rem;
    float: right;
    text-align: center;
    color #fff
    .arow-icon {
      margin-left: -0.04rem;
      font-size: 0.24rem;
    }
  }
}
</style>
