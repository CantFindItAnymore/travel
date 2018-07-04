<template>
  <div>
    <router-link to="/">
      <div
        class="header-left"
        v-show="headerLeftShow"
    >
        <span class="iconfont header-left-back">&#xe697;</span>
      </div>
    </router-link>
    <div
      class="header-title"
      v-show="this.titleShow"
      :style="style"
    >
      <router-link to="/">
        <div class="title-left">
          <span class="iconfont title-left-back">&#xe697;</span>
        </div>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      headerLeftShow: true,
      style: {
        opacity: 0
      }
    }
  },
  computed: {
    titleShow () {
      return !this.headerLeftShow
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 30 && top < 140) {
        this.headerLeftShow = false
        let opacity = top / 140
        this.style = {
          opacity
        }
      } else if (top <= 30) {
        this.headerLeftShow = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/varibles'
  .header-left
    position: absolute
    width: .8rem
    height: .8rem
    line-height: .8rem
    text-align: center
    top: .1rem
    left: .1rem
    border-radius: .4rem
    background: rgba(0 0 0 .6)
    z-index: 1
    .header-left-back
      color: #fff
      font-size: .4rem
  .header-title
    position: fixed
    height: .9rem
    width: 100%
    line-height: .9rem
    text-align: center
    background: $bgColor
    font-size: .32rem
    color: #fff
    z-index: 1
    .title-left
      position: absolute
      width: .8rem
      height: .8rem
      line-height: .8rem
      text-align: center
      top: .1rem
      left: .1rem
      border-radius: .4rem
      background: rgba(0 0 0 0)
      .title-left-back
        color: #fff
        font-size: .4rem
</style>
