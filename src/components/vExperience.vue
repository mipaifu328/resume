<!--  -->
<template>
  <div class="experience">
    <h1 class="main-title">项目经历</h1>
    <div class="experience-container">
      <swiper :options="swiperOption">
        <swiper-slide v-for="slide in _swiperSlides" :key="slide.index">
          <a class="experience-items" :href="slide.url" target="_blank">
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
          index: 0,
          title: 'Echarts大数据显示',
          url: 'https://github.com/mipaifu328/echarts-deom',
          imgUrl: require('../assets/images/works/echarts-demo-1.png'),
          description: '使用Echarts结合地图显示大数据面板'
        },
        {
          index: 1,
          title: '南沙位置服务项目',
          url: '#',
          imgUrl: require('../assets/images/experience/sharedBikes.png'),
          description: '南沙位置服务项目主要包括：共享单车监管、智慧养老、平安校园三个项目。拥有各自的PC管理系统和App移动应用系统，主要功能包括大数据统计信息展示，位置服务，轨迹监测，一键报警等功能。该项目主要负责的是APP开发和PC后台管理部分功能开发。APP采用DCloud H5+开发，打包发布版本，负责pc首页动态数据界面展示，通过使用Echarts结合高德地图API实现各项数据不同统计类型展示，3D地图建筑动态标注颜色的人流动数量和趋势。'
        },
        {
          index: 2,
          title: '幼儿园应用APP',
          url: 'https://www.mipaifu328.com/weuiDemo/kindergarten/',
          imgUrl: require('../assets/images/experience/yey.png'),
          description: '为增强幼儿园家长和老师互动，了解小朋友各项在园教育情况。记录成长印记等功能。该项目运行于微信公众号，同时拥有对应微信小程序和后台管理系统。主要技术采用weui，H5，css3，zepto，iscroll等技术，运用Mock实现前端模拟接口开发。后台管理系统采用bootstrap编写，页面兼容ie8和多浏览器。'
        }, {
          index: 3,
          title: '广东省交通厅移动办公平台',
          url: '#',
          imgUrl: require('../assets/images/experience/jtt-app.png'),
          description: '一款为方便交通厅日常移动办公的 App。可以查看处理公文，事务，通知，邮件，设置个人日程，个性化文件柜等功能。项目采用MUI H5+框架，结合使用原生JS，将H5页面打包成为APP。采用localstorage对文件夹，文件名进行本地存储。使用mui H5+提供的sdk操作IO、Downloader、Camera等，通过接口调用安卓和ios原生方法。页面布局和样式兼容ios和安卓两端。'
        }, {
          index: 4,
          title: '广东省交通运输厅公众网',
          url: 'http://www.gdcd.gov.cn/',
          imgUrl: require('../assets/images/experience/gdcd.jpg'),
          description: '广东省交通运输厅公众网，页面布局兼容各种浏览器和低版本浏览器。其中嵌套集成网上订票，客运情况查询，高速路费查询，阳光政务等系统功能。同时拥有手机wap版，采用zepto，iscroll实现主要的几个重要栏目的展示。其中还包括制作每年的春运专题页面、投票页面，集合腾讯地图等功能。'
        }, {
          index: 5,
          title: '广东省交通运输厅公众网手机版',
          url: 'http://www.gdcd.gov.cn/index.jhtml?mobile=true',
          imgUrl: require('../assets/images/experience/gdcd-mobile.jpg'),
          description: '广东省交通运输厅公众网手机版，主要通过手机访问公众网时，能将几个比较重要的栏目在手机上展示和查看。采用h5，zepto和iscroll实现。'
        }, {
          index: 6,
          title: '阳光政务等多平台和微信公众号页面',
          url: 'http://ygzw.gdcd.gov.cn/',
          imgUrl: require('../assets/images/experience/ygzw.jpg'),
          description: '广东省交通厅阳光政务，2016春运专题，2017春运专题，广东省感动交通人物投票等网站。主要负责的网站页面开发和维护工作。根据效果图编写前端页面，采用html，css，js，jQuery，兼容ie8和多浏览器样式问题，与后台数据交互等。同时使用zepto，iscroll开发对应网站微信公众号页面。'
        }, {
          index: 7,
          title: '广东省交通运输厅数字档案',
          url: '#',
          imgUrl: require('../assets/images/experience/archives.png'),
          description: '广东省交通运输厅数字档案、广东省交通运输厅公文交换系统：对easyui API的使用，同时根据需求优化系统图标，自定义样式表，增加顶部导航并和菜单栏进行联动。在一些特殊的页面采用原生JS和H5进行编写。同时单独开发附件上传功能，为了兼容ie低版本浏览器，采用Flex实现多附件断点续传功能，运用Flex与java、javascript交互。'
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
<style lang="scss" scoped>
  .experience-container{
    margin: 0 auto;
    max-width: 1000px;
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
        background-position:top left;
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
    }
  }
  @media screen and (min-width: 1500px){
    .experience-container{
      margin: 0 auto;
      max-width: 1400px;
      .experience-items{
        width: 400px;
        height:500px;
      }
    }
  }
</style>
