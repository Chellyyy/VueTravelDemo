<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="(item, index) of list" :key="index">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl"/>
        </div>

        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">
            {{item.desc}}
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import RecomendStar from '../components/Star'
export default {
  name: 'HomeWeekend',
  components: {
    RecomendStar
  },
  props: {
    list: Array
  },
  data () {
    return {
      // recommendList: [
      //   {
      //     id: '0001',
      //     title: '温泉必游',
      //     imgUrl: 'http://img1.qunarzz.com/sight/source/1811/ed/bf2bc72af591d5.jpg_r_640x214_f9f1bfcc.jpg',
      //     desc: '为你量身打造绿色健康生活方式，远离都市的喧嚣，工作的烦恼，还你一个悠闲静雅之旅'
      //   },
      //   {
      //     id: '0002',
      //     title: '南京必打卡',
      //     imgUrl: 'http://img1.qunarzz.com/sight/source/1505/f1/ae9d4299b8aaea.jpg_r_640x214_0c555905.jpg',
      //     desc: '看尽王侯将相荣辱成败，六朝金粉潮起潮落'
      //   },
      //   {
      //     id: '0003',
      //     title: '民国情怀国共风华',
      //     imgUrl: 'http://img1.qunarzz.com/sight/source/1505/e1/cdbf56d837da59.jpg_r_640x214_105fc3f2.jpg',
      //     desc: '南京，一座历史文化名城，这片土地上曾经经历过太多太多值得我们去追忆的往事'
      //   }
      // ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
  .title
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item-img-wrapper
    height: 0
    overflow: hidden
    padding-bottom: 37.09%
  .item-img
    width: 100%
  .item-info
    flex: 1
    min-width: 0
    padding: .1rem
    .item-title
      font-size: .35rem
      margin-top: .2rem
      ellipsis()
    .item-desc
      margin: .2rem 0rem
      font-size .25rem
      color: $darkText
      ellipsis()
</style>
