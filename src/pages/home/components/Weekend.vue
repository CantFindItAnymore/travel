<template>
  <div>
    <div class="title">
      周末去哪儿
    </div>
    <ul>
      <li class="recommend-item border-bottom" v-for="item of weekendList" :key="item.id">
        <div class="recommend-item-img-wrapper">
          <img class="recommend-item-img" :src="item.imgUrl"/>
        </div>
        <div class="recommend-item-info">
          <p class="recommend-item-title">{{item.title}}</p>
          <p class="recommend-item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/mixins'
  .title
    line-height: .8rem
    text-indent: .2rem
    background: #eee
    margin-top: .2rem
    font-size: .3rem
  .recommend-item-img-wrapper
    height: 0
    padding-bottom: 37.09%
    overflow: hidden
    .recommend-item-img
      width: 100%
  .recommend-item-info
    padding: .1rem
    min-width: 0
  .recommend-item-title
    ellipsis()
    line-height: .44rem
    font-size: .3rem
    font-weight: bolder
  .recommend-item-desc
    ellipsis()
    line-height: .44rem
    color: #ccc
</style>
