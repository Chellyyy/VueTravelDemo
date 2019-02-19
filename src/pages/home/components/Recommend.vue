<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li"
                   class="item border-bottom"
                   v-for="(item, index) of list"
                   :key="index"
                   :to='"/detail/" + item.id'
      >
        <img class="item-img" :src="item.imgUrl"/>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-like">
            <recomend-star class="item-like-stars" :point="item.point"></recomend-star>
            <span class="item-like-comment">{{item.comment}}</span>条评论
          </p>
          <p class="item-price">
            <span class="price">￥<span class="price-em">{{item.price}}</span></span>起
          </p>
          <!--<button class="item-button">查看详情</button>-->
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
import RecomendStar from '../components/Star'
export default {
  name: 'HomeRecommend',
  components: {
    RecomendStar
  },
  props: {
    list: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
.title
  margin-top: .2rem
  line-height: .8rem
  background: #eee
  text-indent: .2rem
.item
  padding:.2rem
  display: flex
  height: 1.9rem
  overflow: hidden
  .item-img
    width: 1.7rem
    height: 1.7rem
    padding: .1rem
  .item-info
    flex: 1
    min-width: 0
    .item-title
      font-size: .35rem
      margin-top: .2rem
      ellipsis()
    .item-like
      line-height: .3rem
      height: .3rem
      margin-top: .2rem
      .item-like-stars
        top: -2px
        position: relative
      .item-like-comment
        margin-left: .2rem
    .item-price
      margin-top: .3rem
      .price
        color: $priColor
        .price-em
          font-size: .4rem
          margin-left: -0.08rem;
</style>
