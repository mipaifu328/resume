<!--  -->
<template>
  <div class="work">
    <h1 class="main-title">作品集</h1>
    <div class="work-wrapper">
      <swiper :options="swiperOption" ref="mySwiper" @slideChange="slideChange">
        <swiper-slide v-for="slide in swiperSlides" :key="slide.index">
          <a class="work-items" :href="slide.url">
            <div class="work-title">{{slide.title}}</div>
            <img :src="slide.imgUrl"/>
          </a>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"> </div>
      </swiper>
    </div>
    <div class="works-description">
      <p>{{currentWorkDescription}}</p>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        effect: 'cube'
      },
      swiperSlides: [
        {
          index: 1,
          title: '个人简历页面',
          url: 'http://www.mipaifu328.com/resume/dist/',
          imgUrl: require('../assets/images/works/resume.png'),
          description: '使用vue编写的个人简历页面'
        }, {
          index: 2,
          title: '基于bootstrap后台管理界面',
          url: 'http://www.mipaifu328.com/adminDemo/kindergartenLeaderPC/',
          imgUrl: require('../assets/images/works/admin-mobile.png'),
          description: '基于bootstrap后台管理界面'
        }, {
          index: 3,
          title: 'VUE防酷狗音乐3',
          url: 'https://github.com/mipaifu328/vue-kugou-demo',
          imgUrl: require('../assets/images/works/kugou.png'),
          description: '使用vue仿写酷狗音乐，采用vue-cli工具构建,同时使用了vue-router,vuex等技术。'
        }, {
          index: 4,
          title: '微信小程序-天气查询',
          url: 'https://github.com/mipaifu328/wx-weather',
          imgUrl: require('../assets/images/works/wx-weather.png'),
          description: '微信小程序开发简单的天气查询应用，地理编码、天气数据均来自百度地图开放平台。'
        }
      ],
      activeIndex: 1
    }
  },
  computed: {
    currentWorkDescription () {
      return this.swiperSlides[this.activeIndex - 1].description
    },
    swiper () {
      // 通过refs获取swiper对象
      return this.$refs.mySwiper.swiper
    }
  },
  methods: {
    slideChange: function () {
      let activeIndex = this.swiper.activeIndex
      // 超出长度设置为1，loop循环时activeIndex最后一个会变成length+1
      if (activeIndex <= this.swiperSlides.length) {
        this.activeIndex = activeIndex
      } else {
        this.activeIndex = 1
      }
    }
  }
}

</script>
<style scoped>
  .work{
    width: 100%;
    max-width: 1000px;
    margin: 0 auto;
    text-align: center;
  }
  .work .main-title{
    top: 20px;
  }
  .work-wrapper{
    display: inline-block;
    margin: 20px;
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
  .works-description{
    display: inline-block;
    width: 50%;
    margin-left:100px;
    height: 568px;
    background: rgba(255, 255, 255, 0.8);
    border-radius: 8px;
  }
  @media screen and (max-width: 960px) and (min-width: 768px){
    .works-description{
      width:320px;
      margin-left:40px;
    }
  }
  @media screen and (max-width: 768px){
    .work-wrapper{
      display: block;
      margin: 6vh auto;
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
    .works-description{
      display: none;
    }
  }
</style>
