<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item, index) of recommendList" :key="index">
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
      </li>
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          title: '大报恩寺遗址公园',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1512/95/9579bcb3e5a206cc90.water.jpg_200x200_aaa2ccea.jpg',
          point: '5.0',
          price: '40',
          comment: '15157'
        },
        {
          id: '0002',
          title: '秦淮灯会主会场（白鹭洲公园）',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1901/5a/5a10cf85846813f8a3.img.jpg_200x200_ce922862.jpg',
          point: '4.5',
          price: '45',
          comment: '25771'
        },
        {
          id: '0003',
          title: '南京汤山颐尚温泉',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/f4/f455d92ba582f608.water.jpg_200x200_375e5775.jpg',
          point: '5.0',
          price: '127',
          comment: '12588'
        }
      ]
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
