<template>
  <div>
    <div class="title">
      热销推荐
    </div>
    <ul>
      <li class="recommend-item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="recommend-item-img" :src="item.imgUrl"/>
        <div class="recommend-item-info">
          <p class="recommend-item-title">{{item.title}}</p>
          <p class="recommend-item-desc">{{item.desc}}</p>
          <button class="recommend-item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: 1,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1609/7a/7ae8ee7831836095a3.water.jpg',
          title: '金海湖风景区',
          desc: '1290条评论'
        },
        {
          id: 2,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1609/7a/7ae8ee7831836095a3.water.jpg',
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
  .recommend-item
    position: relative
    display: flex
    .recommend-item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem .1rem 0 .1rem
    .recommend-item-info
      flex: 1
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
    .recommend-item-button
      background: #FFD12C
      border-radius: .06rem
      position: absolute
      bottom: 0
</style>
