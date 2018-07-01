<template>
  <ul class="alphabet">
    <li
      class="item"
      v-for="(item, key) of city"
      :key="key"
    >
      {{key}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    city: Object
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
