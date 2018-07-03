<template>
  <div>
    <div class="search">
      <input type="text" v-model="keyword" class="search-input" placeholder="请输入城市名或拼音"/>
    </div>
    <div class="search-result" v-show="keyword" ref="search">
      <ul>
        <li
          class="search-result-item border-bottom"
          v-for="item of list"
          :key="item.id"
        >
          {{item.name}}
        </li>
        <li
          class="search-result-item border-bottom"
          v-show="hasnoresult"
        >
          没有找到向相关数据
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    city: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasnoresult () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (!this.keyword) {
        this.list = []
        this.hasresult = false
        return
      }
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let item in this.city) {
          this.city[item].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 ||
            value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/varibles.styl'
  .search
    height: .72rem
    padding: 0 .1rem
    background: $bgColor
    .search-input
      box-sizing: border-box
      height: .62rem
      line-height: .62rem
      width: 100%
      text-align: center
      border-radius: .06rem
      color: #666
      padding: 0 .1rem
  .search-result
    z-index: 1
    overflow: hidden
    position absolute
    top: 1.58rem
    bottom: 0
    left: 0
    right: 0
    background: #fff
    .search-result-item
      background: $bgColor
      height: .62rem
      line-height: .62rem
      padding-left: .2rem
</style>
