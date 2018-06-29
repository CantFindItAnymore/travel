<template>
  <div>
    <div class="title">
      周末去哪儿
    </div>
    <ul>
      <li class="recommend-item border-bottom" v-for="item of recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [
        {
          id: 1,
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
          title: '金海湖风景区',
          desc: '1290条评论'
        },
        {
          id: 2,
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
          title: '金海湖风景区',
          desc: '1290条评论'
        }
      ]
    }
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
    padding-bottom: 34%
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
