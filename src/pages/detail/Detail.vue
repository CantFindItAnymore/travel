<template>
  <div>
    <DetailHeader/>
    <DetailBanner
      :sightName="sightName"
      :bannerImg="bannerImg"
      :gallaryImgs="gallaryImgs"
    />
    <div class="conte">
      <DetailList
        :categoryList="categoryList"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
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
      lastListId: '',
      currentListId: this.$route.params.id,
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      categoryList: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      })
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
      res = res.data
      if (res.ret === true && res.data) {
        this.sightName = res.data.sightName
        this.bannerImg = res.data.bannerImg
        this.gallaryImgs = res.data.gallaryImgs
        this.categoryList = res.data.categoryList
      }
    }
  },
  activated () {
    if (this.lastListId !== this.$route.params.id) {
      this.lastListId = this.$route.params.id
      this.getDetailInfo()
    }
  }
}
</script>

<style lang='stylus' scoped>
  .conte
    height: 50rem
</style>
