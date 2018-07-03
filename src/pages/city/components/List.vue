<template>
  <div class="list" ref="list">
    <div>
      <!-- 当前城市 -->
      <div class="area">
        <div class="title border-topbottom">
          当前城市
        </div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">
              {{this.currentCity}}
            </div>
          </div>
        </div>
      </div>
      <!-- 热门城市 -->
      <div class="area">
        <div class="title border-topbottom">
          热门城市
        </div>
        <div class="button-list">
          <div
            class="button-wrapper"
            v-for="item of this.hotCity"
            :key="item.id"
            @click="handleClickCityChange(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <!-- 所有城市列表 -->
      <div
        class="area"
        v-for="(item, key) of this.city"
        :key="key"
        :ref="key"
      >
        <div class="title border-topbottom">
          {{key}}
        </div>
        <div class="city-list">
          <div
            class="city border-bottom"
            v-for="member of item"
            :key="member.id"
            @click="handleClickCityChange(member.name)"
          >
            {{member.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {mapState} from 'vuex'
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    city: Object,
    hotCity: Array,
    letter: String
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.list)
  },
  computed: {
    ...mapState({currentCity: 'city'})
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  methods: {
    handleClickCityChange (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    }
  }
}
</script>

<style lang='stylus' scoped>
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .list
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    overflow: hidden
  .title
    height: .64rem
    line-height: .64rem
    font-size: .26rem
    background: #eee
    color: #666
    padding-left: .2rem
  .button-list
    padding: .1rem .6rem .1rem .1rem
    overflow: hidden
    .button-wrapper
      float: left
      width: 33.33%
    .button
      margin: .1rem
      padding: .1rem
      text-align: center
      border: .01rem solid #ccc
      border-radius: .06rem
  .city-list
    .city-wrapper
    .city
      height: .76rem
      line-height: .76rem
      padding-left: .2rem
</style>
