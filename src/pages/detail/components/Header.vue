<template>
    <div>
      <div class="header-abs iconfont" v-show="absShow">&#xe624;</div>
      <div class="header-fixed" v-show="!absShow" :style="opacityStyle">
        detail
        <router-link to="/">
          <div class="iconfont header-fixed-back">&#xe624;</div>
        </router-link>
      </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      absShow: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.scrollingElement.scrollTop
      if (top > 60) {
        this.absShow = false
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
      } else {
        this.absShow = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header-abs
  position: absolute;
  left: .2rem
  top: .2rem
  width: .8rem
  height: .8rem
  border-radius: .4rem
  background: rgba(0, 0, 0, .5)
  line-height:.8rem
  text-align: center
  color: #fff
.header-fixed
  z-index: 2
  position: fixed
  top: 0
  left: 0
  right: 0
  font-size: .32rem
  overflow: hidden
  height: $headerHeight
  line-height: $headerHeight
  text-align: center
  color: #ffffff
  background: $bgColor
  .header-fixed-back
    position: absolute
    top: 0
    left: 0
    width: .64rem
    text-align: center
    font-size .4rem
    color: #fff
</style>
