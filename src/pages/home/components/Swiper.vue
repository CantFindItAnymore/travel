<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper_img" :src="item.imgUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: 1,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg'
        },
        {
          id: 2,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/38/ab7ab660adc68602.jpg_750x200_e8fde60e.jpg'
        }
      ]
    }
  }
}
</script>

<style lang='stylus' scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: white
  .wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 26.6%
    background-color: skyblue
    .swiper_img
      width: 100%
</style>
