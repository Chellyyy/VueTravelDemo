<template>
    <div>
      <detail-banner :title="title" :img="img" :imgs="imgs"></detail-banner>
      <detail-header></detail-header>
      <detail-list :list="list"></detail-list>
      <div class="content"></div>
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
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [],
      title: '',
      img: '',
      imgs: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json?id=', {
        params: {
          id: this.$route.params.id
        }
      })
        .then(this.handleDetailInfo)
    },
    handleDetailInfo (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.title = data.sightName
        this.img = data.bannerImg
        this.imgs = data.galleryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
.content
  height: 50rem
</style>
