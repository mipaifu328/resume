<!--  -->
<template>
  <div class="experience">
    <h1 class="main-title">项目经历</h1>
    <div class="experience-container">
      <swiper :options="swiperOption">
        <swiper-slide v-for="slide in _swiperSlides" :key="slide.index">
          <a class="experience-items" :href="slide.url">
            <div class="experience-title">{{slide.title}}</div>
            <div class="experience-img" :style="slide.style"/>
            <div class="experience-des">
              {{slide.description}}
            </div>
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
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 0,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        },
        breakpoints: {
          1024: {
            slidesPerView: 3
          },
          768: {
            slidesPerView: 1
          }
        }
      },
      swiperSlides: [
        {
          index: 1,
          title: '广东省交通厅移动办公平台',
          url: '#',
          imgUrl: require('../assets/images/experience/jtt-app.png'),
          description: '一款为方便交通厅日常移动办公的 App。可以查看处理公文，事务，通知，邮件，设置个人日程，个性化文件柜等功能。采用MUI H5+框架，结合使用原生JS，将H5页面打包成为APP，实现一套代码苹果安卓两端通用。'
        }, {
          index: 2,
          title: '幼儿园应用APP',
          url: 'http://www.mipaifu328.com/weuiDemo/kindergarten/',
          imgUrl: require('../assets/images/experience/yey.png'),
          description: '为增强幼儿园家长和老师互动，了解小朋友各项在园教育情况。记录成长印记等功能，项目运行于微信公众号，采用WEUI，HTML5，CSS3, 运用Mock实现前端模拟接口开发。'
        }, {
          index: 3,
          title: 'VUE防酷狗音乐3',
          url: '#',
          imgUrl: require('../assets/images/mipaifu328.jpg'),
          description: '描述信息3'
        }, {
          index: 4,
          title: 'VUE防酷狗音乐4',
          url: '#',
          imgUrl: require('../assets/images/mipaifu328.jpg'),
          description: '描述信息4'
        }, {
          index: 5,
          title: 'VUE防酷狗音乐5',
          url: '#',
          imgUrl: require('../assets/images/mipaifu328.jpg'),
          description: '描述信息5'
        }
      ]
    }
  },
  computed: {
    _swiperSlides () {
      return this.swiperSlides.filter(item => {
        item['style'] = 'background-image:url(' + item.imgUrl + ')'
        return item
      })
    }
  }
}

</script>
<style scoped>
  .experience-container{
    margin: 0 auto;
    max-width: 1000px;
  }
  .experience-items{
    position: relative;
    display: block;
    margin: 0 auto;
    margin-bottom: 50px;
    padding: 20px;
    width:300px;
    height:400px;
    border-radius: 6px;
    background-color:#fff;
    box-sizing: border-box;
    color:#000;
    overflow: hidden;
  }
  .experience-title{
    background-color: rgba(0, 0, 0, .8);
    color: #fff;
    text-align: center;
    height: 30px;
    line-height: 30px;
    position: absolute;
    top: 20px;
    left: 20px;
    right: 20px;
    bottom: 50px;
  }
  .experience-img{
    width: 100%;
    height: 100%;
    background-position:top center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  .experience-des{
    position: absolute;
    left: 20px;
    right: 20px;
    bottom: 20px;
    font-size: 14px;
    line-height: 24px;
    text-indent: 2em;
    text-align: justify;
    padding: 0 8px;
    color: #fff;
    background: rgba(0, 0, 0, .6);
  }
</style>
