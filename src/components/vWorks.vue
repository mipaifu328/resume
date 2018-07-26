<!--  -->
<template>
  <div class="work">
    <h1 class="main-title">作品集</h1>
    <div class="work-mobile" v-if="isMobile">
      <swiper :options="swiperOption" ref="mySwiper" @slideChange="slideChange">
        <swiper-slide v-for="slide in swiperSlides" :key="slide.index">
          <a class="work-items" :href="slide.url" target="_blank">
            <div class="work-title">{{slide.title}}</div>
            <img :src="slide.imgUrl">
          </a>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"> </div>
      </swiper>
    </div>
    <ul class="works-pc" v-if="!isMobile">
      <li class="work-items" v-for="slide in swiperSlides" :key="slide.index">
        <a :href="slide.url" target="_blank">
          <img :src="slide.imgUrl">
          <div class="work-items-txt">
            <h2 class="work-title">{{slide.title}}</h2>
            <p>{{slide.description}}</p>
          </div>
        </a>
      </li>
    </ul>
    <a class="more" href="https://github.com/mipaifu328/" target="_blank">github上面查看更多</a>
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
          url: 'https://www.mipaifu328.com/resume/dist/',
          imgUrl: require('../assets/images/works/resume.png'),
          description: '使用vue编写的个人简历页面'
        }, {
          index: 2,
          title: '基于bootstrap后台管理界面',
          url: 'https://www.mipaifu328.com/adminDemo/kindergartenLeaderPC/',
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
      activeIndex: 1,
      isMobile: false
    }
  },
  computed: {
    // currentWorkDescription () {
    //   return this.swiperSlides[this.activeIndex - 1].description
    // },
    // swiper () {
    //   // 通过refs获取swiper对象
    //   return this.$refs.mySwiper.swiper
    // }
  },
  methods: {
    // slideChange: function () {
    //   let activeIndex = this.swiper.activeIndex
    //   // 超出长度设置为1，loop循环时activeIndex最后一个会变成length+1
    //   if (activeIndex <= this.swiperSlides.length) {
    //     this.activeIndex = activeIndex
    //   } else {
    //     this.activeIndex = 1
    //   }
    // },
    checkIsMobile: function () {
      let width = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth
      this.isMobile = width <= 768
    }
  },
  mounted () {
    // let width = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth
    // this.isMobile = width <= 768
    // window.onresize = () => {
    //   // 这里如果不是用箭头函数的话，this指向的不是vue实例，而是window
    //   let width = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth
    //   this.isMobile = width <= 768
    // }
    this.checkIsMobile()
    window.onresize = this.checkIsMobile
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
  .work-mobile{
    display: block;
    margin: 6vh auto;
    width: 60vw;
    height: 60vh;
    user-select: none;
  }
  .work-mobile .work-items{
    display:block;
    width: 60vw;
    height: 60vh;
    overflow: hidden;
  }
  .work-mobile img{
    width: 100%;
  }
  .work-mobile .work-title{
    background: #272822;
    color: #fff;
    height: 30px;
    line-height: 30px;
    font-size: 12px;
    text-indent: 1em;
  }
  .works-pc{
    width: 100%;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
  .works-pc .work-items{
    width: 47%;
    height:200px;
    margin-bottom: 50px;
    overflow: hidden;
    box-shadow: 0 3px 10px rgba(0,0,0,.2);
    border-radius: 6px;
    transition: box-shadow .3s ease;
  }
  .works-pc .work-items:hover{
    box-shadow: 0 8px 15px rgba(0,0,0,.2);
  }
  .works-pc .work-items a{
    padding: 10px;
    display: flex;
    width: 100%;
    height: 100%;
    background: #fff;
    box-sizing: border-box;
  }
  .works-pc img{
    width: 120px;
    box-shadow: 0 0 2px rgba(0,0,0,.2);
  }
  .works-pc .work-items-txt{
    flex: 1;
    padding-left: 10px;
  }
  .work-items-txt h2{
    margin: 0;
    font-size:20px;
    color: #566270;
    text-align: left;
  }
  .work-items-txt p{
    margin-top: 10px;
    color: #666;
    font-size: 16px;
    line-height: 24px;
    text-align: justify;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 6;
    overflow: hidden;
  }
  .more{
    margin-top:10px;
    text-align: center;
    color: #fff;
  }

  @media screen and (min-width: 1500px){
    .work{
      width: 100%;
      max-width: 1400px;
      margin: 0 auto;
      text-align: center;
    }
    .works-pc .work-items{
      height: 260px;
    }
    .works-pc .work-items a{
      padding: 20px;
    }
    .works-pc img{
      width: 150px;
    }
    .works-pc .work-items-txt{
      padding-left: 20px;
    }
    .work-items-txt h2{
      font-size:24px;
    }
    .work-items-txt p{
      font-size: 18px;
      line-height: 30px;
    }
  }
</style>
