<template>
    <div class="warpper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item in swiperList"
                          :key=item.id>
                <img class="swiper-img" :src="item.imgUrl" alt="">
            </swiper-slide>
                <!-- Optional controls -->
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
      swiperList: [
        {
          id: 0,
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1809/83/a77595fb02eed602.jpg_750x200_1627b072.jpg'
        },
        {
          id: 1,
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1809/39/3340e0b74c892002.jpg_750x200_f1e02a4d.jpg'
        }
      ]
    }
  },
  mounted() {},
  methods: {}
}
</script>
<style lang='stylus' scoped>
.warpper >>> .swiper-pagination-bullet-active
    background #fff
.warpper
    overflow hidden
    width 100%
    height 0
    padding-bottom 31.25%
    .swiper-img
        width 100%
</style>
