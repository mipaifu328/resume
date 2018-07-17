<!--  -->
<template>
  <div class="work">
    <h1>作品集</h1>
    <div class="work-wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="slide in swiperSlides" :key="slide.index">
          <a class="work-items" :href="slide.url">
            <div class="work-title">{{slide.title}}</div>
            <img :src="slide.imgUrl"/>
          </a>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  data () {
    return {
      swiperOption: {
        loop: true,
        effect: 'cube'
      },
      swiperSlides: [
        {
          index: 1,
          title: 'VUE防酷狗音乐1',
          url: '#',
          imgUrl: 'https://github.com/mipaifu328/vue-kugou-demo/raw/master/img_md/img1.png'
        }, {
          index: 2,
          title: 'VUE防酷狗音乐2',
          url: '#',
          imgUrl: 'https://github.com/mipaifu328/vue-kugou-demo/raw/master/img_md/img2.png'
        }, {
          index: 3,
          title: 'VUE防酷狗音乐3',
          url: '#',
          imgUrl: 'https://github.com/mipaifu328/vue-kugou-demo/raw/master/img_md/img3.png'
        }, {
          index: 4,
          title: 'VUE防酷狗音乐4',
          url: '#',
          imgUrl: 'https://github.com/mipaifu328/vue-kugou-demo/raw/master/img_md/img4.png'
        }, {
          index: 5,
          title: 'VUE防酷狗音乐5',
          url: '#',
          imgUrl: 'https://github.com/mipaifu328/vue-kugou-demo/raw/master/img_md/img5.png'
        }
      ]
    }
  },
  components: {
    swiper,
    swiperSlide
  }
}

</script>
<style scoped>
  .work h1{
    font-size: 18px;
    text-align: center;
  }
  .work-wrapper{
    margin: 20px auto;
    width: 320px;
    height: 568px;
    user-select: none;
  }
  .work-items{
    display:block;
    width: 320px;
    height: 568px;
    overflow: hidden;
  }
  .work-title{
    background: #272822;
    color: #fff;
    height: 50px;
    line-height: 50px;
    font-size: 16px;
    text-indent: 1em;
  }
  .work-wrapper img{
    width: 100%;
  }

  @media screen and (max-width: 500px){
    .work-wrapper{
      margin: 10vh auto;
      width: 60vw;
      height: 60vh;
    }
    .work-items{
      display:block;
      width: 60vw;
      height: 60vh;
      overflow: hidden;
    }
    .work-title{
      background: #272822;
      color: #fff;
      height: 30px;
      line-height: 30px;
      font-size: 12px;
      text-indent: 1em;
    }
  }
</style>
