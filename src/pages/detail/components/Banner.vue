<template>
  <div>
    <div class="banner" @click="showGallary">
      <img class="banner-img"
        src="//img1.qunarzz.com/sight/p0/201309/24/977fea7b3c5cd758c8d65eac.jpg_600x330_0f80adad.jpg"/>
        <div class="banner-info">
          <div class="banner-info-title">
            成都熊猫基地(AAAA景区)
          </div>
          <div class="banner-info-number">
            <span class="iconfont">&#xe6e6;</span>
            14
          </div>
        </div>
    </div>
    <CommonGallary
      :imgs="imgs"
      v-show="swiperShow"
      @hideGallary = "hideGallary"
    />
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      imgs: [
        '//img1.qunarzz.com/sight/p0/201309/24/977fea7b3c5cd758c8d65eac.jpg_600x330_0f80adad.jpg',
        '//img1.qunarzz.com/sight/p0/201309/24/977fea7b3c5cd758c8d65eac.jpg_600x330_0f80adad.jpg',
        '//img1.qunarzz.com/sight/p0/201309/24/977fea7b3c5cd758c8d65eac.jpg_600x330_0f80adad.jpg'
      ],
      swiperShow: false
    }
  },
  methods: {
    hideGallary () {
      this.swiperShow = false
    },
    showGallary () {
      this.swiperShow = true
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      bottom: 0
      right: 0
      color: #fff
      padding: 0 .1rem .1rem .1rem
      font-size: .3rem
      background-image: linear-gradient(top, rgba(0 0 0 0 ), rgba(0 0 0 .8))
      .banner-info-title
        flex: 1
      .banner-info-number
        width: .8rem
        border-radius: .1rem
        padding: 0 .1rem
        background: rgba(0 0 0 .6)
</style>
