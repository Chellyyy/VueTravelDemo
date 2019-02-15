<template>
  <span>
    <span class="star-default" v-for="(item, index) of score" :key="index">
      <span v-if="item===1" class="iconfont active">&#xe6d5;</span>
      <span v-else-if="item===2" class="iconfont half-active">&#xe6d5;</span>
      <span v-else class="iconfont ">&#xe6d5;</span>
    </span>
  </span>
</template>

<script>
export default {
  name: 'Star',
  props: ['point'],
  computed: {
    score: function () {
      let stars = this.point
      var num = stars.toString().substring(0, 1)
      var half = stars.toString().substring(1, 2)
      var array = []
      for (var i = 1; i <= 5; i++) {
        if (i <= num) {
          array.push(1)
        } else {
          array.push(0)
        }
      }
      if (half > 0) {
        array[parseInt(num)] = 2
      }
      return array
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
.star-default
  color: #ccc
  .iconfont
    font-size .15rem
.active
  color: #f1a80c
.half-active
  display: inline-block;
  color: #ccc;
  font-family: '微软雅黑';
  background-image: -webkit-gradient(linear, left center,right center, from($priColor), to(#cccccc));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
</style>
