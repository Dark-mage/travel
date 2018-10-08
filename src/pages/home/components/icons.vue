<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages"
                    :key="index">
        <div class="icon"
             v-for="item in page"
             :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content"
                 :src="item.imgUrl"
                 alt="">
          </div>
          <p class="icon-desc">{{item.text}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"
           slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      iconList: [
        {
          id: 0,
          text: '热门景点',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
        },
        {
          id: 1,
          text: '一日游',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png'
        },
        {
          id: 2,
          text: '必游之地',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
        },
        {
          id: 3,
          text: '打卡圣地',
          imgUrl:
            'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png'
        },
        {
          id: 4,
          text: '赏秋色',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1803/ea/01d081dacb03cc02.png'
        },
        {
          id: 5,
          text: '普陀山',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1805/57/1e29afd06f881102.png'
        },
        {
          id: 6,
          text: '欢乐谷',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png'
        },
        {
          id: 7,
          text: '动物园',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png'
        },
        {
          id: 8,
          text: '一日游',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png'
        },
        {
          id: 9,
          text: '必游之地',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
        }
      ]
    }
  },
  computed: {
    pages() {
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
  },
  methods: {}
}
</script>
<style lang='stylus' scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons >>> .swiper-container
  height 0
  padding-bottom 50%
.icons >>> .swiper-pagination-bullet-active
  background #fff
.icon
  position relative
  overflow hidden
  float left
  width 25%
  height 0
  padding-bottom 25%
  .icon-img
    position absolute
    top 0
    left 0
    right 0
    bottom 0.44rem
    box-sizing border-box
    padding 0.1rem
    .icon-img-content
      display block
      margin 0 auto
      height 100%
  .icon-desc
    position absolute
    left 0
    right 0
    bottom 0
    height 0.44rem
    line-height 0.44rem
    text-align center
    color $darkTextColor
    ellipsis()
</style>
