<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/4642f3d4ca2aaaa3c7c522f9eb86fdc7.jpg_750x200_5a390d78.jpg'
        },
        {
          id: '0002',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/c24c9a91c6d4267ab3b935e6de37feae.jpg_750x200_26a5b2db.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus"  scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff
.wrapper
  width: 100%
  height:0
  overflow: hidden
  padding-bottom: 26.67%
  background: #eee
  .swiper-img
    width: 100%

</style>
