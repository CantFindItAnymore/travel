<template>
  <div class="header">
    <div class="header_left">
      <span class="iconfont">&#xe697;</span>
    </div>
    <div class="header_input">
      <span class="iconfont">&#xe693;</span>
      输入城市/景点/游玩主题
    </div>
    <div class="header_right">
      {{this.city}}
      <span class="iconfont arrow_icon">&#xe6dc;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
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
    .header_left
      width: .64rem
      float: left
      text-align: center
    .header_input
      flex: 1
      color: #B6B8BB
      padding-left: .2rem
      height:.64rem
      line-height: .64rem
      background-color: white
      border-radius: .1rem
      margin-top: .12rem
      margin-left: .1rem
    .header_right
      width: 1.24rem
      float: right
      text-align: center
      .arrow_icon
        font-size: .2rem
</style>
