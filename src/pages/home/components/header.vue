<template>
  <div class="header">
    <div class="header_left">返回</div>
    <div class="header_input">搜索</div>
    <div class="header_right">选择</div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang='stylus' scoped>
  .header
    background-color: skyblue
    color: black
    display: flex
    line-height: .86rem
    .header_left
      width: .64rem
      float: left
      text-align: center
    .header_input
      flex: 1
      color: #B6B8BB
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
</style>
