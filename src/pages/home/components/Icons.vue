<template>
    <div class="icons">
      <swiper :options="swiperOption">
        <swiper-slide
                      v-for="page of pages"
                      :key="page.id"
        >
          <div class="icon"
               v-for="item of page"
               :key="item.id"
          >
            <div class="icon-img">
              <img class="icon-img-content" :src="item.imgUrl" />
            </div>
            <p class="icon-desc">{{item.desc}}</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
</template>

<script>

export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
      // iconList: [
      //   {
      //     id: '0001',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
      //     desc: '热门景点'
      //   },
      //   {
      //     id: '0002',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
      //     desc: '一日游'
      //   },
      //   {
      //     id: '0003',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
      //     desc: '文化古迹'
      //   },
      //   {
      //     id: '0004',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
      //     desc: '溜娃儿'
      //   },
      //   {
      //     id: '0005',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
      //     desc: '泡温泉'
      //   },
      //   {
      //     id: '0006',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
      //     desc: '夫子庙'
      //   },
      //   {
      //     id: '0007',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
      //     desc: '总统府'
      //   },
      //   {
      //     id: '0008',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
      //     desc: '牛首山'
      //   },
      //   {
      //     id: '0009',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
      //     desc: '明孝陵'
      //   }
      // ]
    }
  },
  computed: {
    pages: function () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
.icons >>> .swiper-container
  overflow: hidden
  height:0
  width: 100%
  padding-bottom: 50%
.icons
  margin-top .1rem
  .icon
    position: relative;
    height: 0
    overflow: hidden
    float: left
    width: 25%
    padding-bottom: 25%
    .icon-img
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-size: border-box
      padding: .1rem
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
    .icon-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .44rem
      line-height: .44rem
      text-align: center
      color: $darkText
      ellipsis()
</style>
