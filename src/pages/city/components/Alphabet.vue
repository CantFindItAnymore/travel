<template>
  <ul class="alphabet">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      :ref="item"
      @click="handleClick"
      @touchstart="handleStart"
      @touchmove="handleMove"
      @touchend="handleEnd"
    >
      {{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    city: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let item in this.city) {
        letters.push(item)
      }
      return letters
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleStart () {
      this.touchStatus = true
    },
    handleMove (e) {
      if (this.touchStatus === true) {
        // A距离的nav下沿的高度
        // const startY = this.$refs['A'][0].offsetTop
        // 触点距离屏幕顶部的高度
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          let touchIndex = Math.floor((touchY - this.startY) / 20)
          if (touchIndex < 0) {
            touchIndex = 0
          }
          console.log(touchIndex)
          console.log(this.letters[touchIndex])
          if (touchIndex && touchIndex >= 0 && touchIndex <= this.letters.length) {
            this.$emit('change', this.letters[touchIndex])
          }
        }, 16)
      }
    },
    handleEnd () {
      this.touchStatus = false
    }
  }
}
</script>

<style lang='stylus' scoped>
  .alphabet
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    right: 0
    top: 1.58rem
    bottom: 0
    width: .4rem
    text-align: center
    .item
      height: .4rem
</style>
