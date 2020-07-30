<template>
	<div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
		name:'HomeSwiper',
		data () {
			return {
				swiperOption: {
        	pagination: '.swiper-pagination',
        	loop: true
      	},
      	swiperList:[{
      		id:'0001',
      		imgUrl:'http://img1.qunarzz.com/sight/p0/1905/af/af4f95f579ee43b1a3.water.jpg_600x330_164b10ec.jpg'
      	},{
      		id:'0002',
      		imgUrl:'http://img1.qunarzz.com/sight/p0/1511/34/34170b200db08a5a90.img.jpg_600x330_9fee26e9.jpg'
      	}]
			}
		}
	}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 53%
    background: #eee
    .swiper-img
      width: 100%
</style>