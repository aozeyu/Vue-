<template>
  <div class="wrapper">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide
        v-for="(item,index) of swiperList" :key="index"><img
          class="swiper-img"
          :src="item.imgUrl"
          alt=""
      /></swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  data() {
    return {
      swiperOptions: {
        pagination: ".swiper-pagination",
        loop:true
      },
      swiperList:[{
        id:'0001',
        imgUrl:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3740323779,2777059388&fm=26&gp=0.jpg'
      },{
        id:'0002',
        imgUrl:'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3427169086,3097665420&fm=26&gp=0.jpg'
      }]
    }
  }
};
</script>

<style lang="stylus" scoped>
.wrapper>>>.swiper-pagination-bullet-active {
  background: #fff !important;
}

.wrapper {
  width: 100%;
  height: 0;
  padding-bottom: 31.25%;
  background: #eee;

  .swiper-img {
    width: 100%;
  }
}
</style>