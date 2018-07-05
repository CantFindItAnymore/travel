<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe697;</span>
    </div>
    <div class="header-input-wrapper">
      <span class="iconfont header-input-icon">&#xe693;</span>
      <input type="text" class="header-input" placeholder="输入城市/景点/游玩主题" />
    </div>
    <router-link to="/city">
      <div class="header-right">
      {{this.city}}
      <span class="iconfont arrow-icon">&#xe6dc;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/varibles'
  .header
    background-color: $bgColor
    color: white
    display: flex
    line-height: .86rem
    .header-left
      width: .64rem
      float: left
      text-align: center
    .header-input-wrapper
      flex: 1
      color: #B6B8BB
      overflow: hidden
      padding-left: .2rem
      padding-right: .2rem
      height:.64rem
      line-height: .64rem
      background-color: white
      border-radius: .1rem
      margin-top: .12rem
      margin-left: .1rem
      .header-input
        height: .64rem
        background-color: white
        position: relative
        left: .2rem
        width: 90%
    .header-right
      min-width: 1.04rem
      padding: 0 .1rem
      float: right
      text-align: center
      color: #fff
      .arrow-icon
        font-size: .2rem
</style>
