<template>
  <div>
    <div>
      <div
        v-for="(item, index) of this.categoryList"
        :key="index"
      >
        <div class="list-title border-bottom">
          <span class="list-title-icon"></span>
          {{item.title}}
        </div>
        <!-- 递归组件 -->
        <div class="list-children" v-if="item.children">
          <DetailList :categoryList="item.children"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    categoryList: Array
  }
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/varibles'
  .list-title
    height: .86rem
    line-height: .86rem
    font-size: .32rem
    padding-left: .1rem
    .list-title-icon
      display: inline-block
      width: .36rem
      height: .36rem
      background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
      margin-right: .1rem
      background-size: .4rem 3rem
  .list-children
    padding-left: .24rem
</style>
