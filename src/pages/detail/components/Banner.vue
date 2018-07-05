<template>
  <div>
    <div class="banner" @click="showGallary">
      <img
        class="banner-img"
        :src="this.bannerImg"
      />
        <div class="banner-info">
          <div class="banner-info-title">
            {{this.sightName}}
          </div>
          <div class="banner-info-number">
            <span class="iconfont">&#xe6e6;</span>
            14
          </div>
        </div>
    </div>
    <CommonFade>
      <CommonGallary
        :gallaryImgs="gallaryImgs"
        v-show="swiperShow"
        @hideGallary = "hideGallary"
      />
    </CommonFade>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import CommonFade from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary,
    CommonFade
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
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
