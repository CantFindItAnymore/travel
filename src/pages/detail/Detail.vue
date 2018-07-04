<template>
  <div>
    <DetailHeader/>
    <DetailBanner/>
    <div class="conte">
      <DetailList :list="list"/>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    DetailHeader,
    DetailBanner,
    DetailList
  },
  data () {
    return {
      list: [
        {
          title: '成人票',
          children: [
            {
              title: '成人票11111',
              children: [
                {title: '成人票11111----1111'},
                {title: '成人票11111----2222'},
                {title: '成人票11111----3333'}
              ]
            },
            {
              title: '成人票22222'
            },
            {
              title: '成人票33333'
            }
          ]
        },
        {
          title: '儿童票'
        },
        {
          title: '特惠票'
        },
        {
          title: '学生票'
        }
      ]
    }
  }
}
</script>

<style lang='stylus' scoped>
  .conte
    height: 50rem
</style>
