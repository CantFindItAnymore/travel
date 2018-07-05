<template>
  <div class="container">
    <div class="img-wrapper" @click="handleClick">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide
          v-for="(item, index) of this.gallaryImgs"
          :key="index"
        >
          <img class="swiper-img" :src="item"/>
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        // 解决swiper宽度计算问题
        observeParents: true,
        observer: true
      }
    }
  },
  props: {
    gallaryImgs: Array
  },
  methods: {
    handleClick () {
      this.$emit('hideGallary')
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles'
  .container >>> .swiper-container
    overflow: inherit
  .container
    z-index: 99
    position: fixed
    top: 0
    left: 0
    bottom: 0
    right: 0
    background: #111
    display: flex
    flex-direction: column
    justify-content: center
    .img-wrapper
      background: $bgColor
      width: 100%
      height: 0
      padding-bottom: 100%
      .swiper-img
        width: 100%
      .swiper-pagination
        color: #fff
        bottom: -1rem
</style>
