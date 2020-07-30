<template>
	<div class="icons" :options="swiperOption">
    <swiper>
        <swiper-slide v-for="(page, index) of pages" :key="index">
          <div
            class="icon"
            v-for="item of page"
            :key="item.id"
          >
            <div class='icon-img'>
              <img class='icon-img-content' :src='item.imgUrl' />
            </div>
            <p class="icon-desc">{{item.desc}}</p>
          </div>
        </swiper-slide>
      </swiper>
  </div>
</template>

<script>
export default {
	name:'HomeIcons',
	data () {
    return {
	     swiperOption: {
	       autoplay: false
	     },
	     iconList:[{
	     	id:'0001',
	     	imgUrl:'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
	     	desc:'景点门票'
	     },{
	     	id:'0002',
	     	imgUrl:'https://imgs.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
	     	desc:'东莞必游'
	     },{
	     	id:'0003',
	     	imgUrl:'https://imgs.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
	     	desc:'泡温泉'
	     },{
	     	id:'0002',
	     	imgUrl:'https://imgs.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
	     	desc:'植物园'
	     },{
	     	id:'0002',
	     	imgUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/184e261814a5d07a5d3d08cd29cf590d.png',
	     	desc:'长隆度假区'
	     },{
	     	id:'0002',
	     	imgUrl:'https://imgs.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png',
	     	desc:'东莞观音山'
	     },{
	     	id:'0002',
	     	imgUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/cba147cf6cfcea7109d0bff6aac6f626.png',
	     	desc:'香市动物园'
	     },{
	     	id:'0002',
	     	imgUrl:'https://imgs.qunarzz.com/piao/fusion/1803/90/59a2f523ee2f9202.png',
	     	desc:'隐贤山庄'
	     },{
	     	id:'0002',
	     	imgUrl:'https://imgs.qunarzz.com/piao/fusion/1803/8c/47630407f70e8302.png',
	     	desc:'龙凤山庄'
	     }]
	   }
  	},
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: .1rem
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
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
        color: $darkTextColor
        ellipsis()
</style>