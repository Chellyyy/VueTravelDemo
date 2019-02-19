<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1512/95/9579bcb3e5a206cc90.water.jpg_600x330_d0807192.jpg" alt="">
      <div class="banner-info">
        <div class="banner-number">
          <span class="iconfont">&#xe616;</span>
          <span>6</span>
        </div>
        <div class="banner-title">大报恩寺遗址公园</div>
      </div>
    </div>
    <common-gallery :imgs="imgs" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallery: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1512/95/9579bcb3e5a206cc90.water.jpg_r_800x800_21dd28bb.jpg', 'http://img1.qunarzz.com/sight/p0/1512/62/62b10f89694c850190.water.jpg_r_800x800_f22eaa3a.jpg']
    }
  },
  components: {
    CommonGallery
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleGalleryClose () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
@import "~styles/varibles.styl"
  .banner
    position: relative;
    overflow: hidden
    height: 0
    padding-bottom:55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute;
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0,0,0,0.1),rgba(0,0,0,0.8))
      .banner-title
        flex: 1
        font-size: .35rem
        padding: .1rem .2rem
      .banner-number
        position: absolute
        bottom: 0
        margin: 0 0 .7rem .2rem
        text-align: center
        width: .6rem
        background: rgba(0,0,0,.5)
        border-radius: .3rem
        padding: .05rem .2rem
        line-height: .32rem
        span
          font-size: .2rem
</style>
