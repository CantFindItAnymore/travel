<template>
  <div>
    <DetailHeader/>
    <DetailBanner/>
    <div class="conte"></div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
export default {
  name: 'Detail',
  components: {
    DetailHeader,
    DetailBanner
  }
}
</script>

<style lang='stylus' scoped>
  .conte
    height: 50rem
</style>
