<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="header-left">
        <span class="iconfont">&#xe697;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    height: .86rem
    line-height: .86rem
    text-align: center
    background: $bgColor
    position: relative
    .header-left
      position: absolute
      top: 0
      left: 0
      width: .64rem
      text-align: center
      color: #fff
</style>
