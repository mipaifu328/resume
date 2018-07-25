<!--  -->
<template>
  <div class="contact">
    <h1 class="main-title">联系我</h1>
    <div class="contact-container">
      <div class="contact-des1">
        <span v-for="item in desList1" :key="item">{{item}}</span>
      </div>
      <div class="contact-des2">
        <p v-for="item in desList2" :key="item">{{item}}</p>
      </div>
      <div class="contact-type">
        <a v-for="item in typeList" :href="item.url" target="_blank" :key="item.name">
          <img :src="item.icon" :alt="item.name">
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      desList1: ['灵感', '代码', '梦想', '未来'],
      desList2: [
        '注重效率，偏爱敏捷开发',
        '喜欢尝试，期待新鲜事物',
        '前端即兴趣，兴趣即未来',
        '行路有良友，便是捷径',
        '带上我吧，一起看到更大的世界'
      ],
      typeList: [{
        name: 'blog',
        url: 'http://www.mipaifu328.com/',
        icon: require('../assets/images/s_blog.svg')
      }, {
        name: 'github',
        url: 'https://github.com/mipaifu328/',
        icon: require('../assets/images/s_github.svg')
      }, {
        name: 'bilibili',
        url: 'https://space.bilibili.com/39265533/',
        icon: require('../assets/images/s_bilibili.png')
      }]
    }
  }
}
</script>

<style scoped>
  .contact-container{
    max-width: 300px;
    margin: 0 auto;
    text-align: center;
  }
  .contact-des1{
    margin: 0 auto;
    display: flex;
    display: flex;
    justify-content: space-between;
    font-size: 22px;
  }
  .contact-des1 span:nth-child(1){
    color: #ff6666;
  }
  .contact-des1 span:nth-child(2){
    color: #3cf;
;
  }
  .contact-des1 span:nth-child(3){
    color: #99FF99;
  }
  .contact-des1 span:nth-child(4){
    color: #FFFFCC;
  }
  .contact-des2{
    margin-top: 40px;
    font-size: 18px;
    color: #fff;
    text-align: center;
  }

  @media screen and (max-width: 768px) {
    .contact-container{
      top: 100px;
      max-width: 250px;
    }
    .contact-des1{
      font-size: 18px;
    }
    .contact-des2{
      margin-top: 50px;
      font-size: 14px;
    }
  }

  .contact-type{
    display: flex;
    justify-content: center;
    margin: 100px auto 0;
  }
  .contact-type a{
    position: relative;
    margin: 0 10px;
    width: 40px;
    height: 40px;
    border: 1px solid #FFF;
    border-radius: 50%;
  }
  .contact-type img{
    width: 65%;
    position: absolute;
    top: 50%;
    right: 50%;
    transform: translateX(50%) translateY(-50%);
  }

  @media screen and (min-width: 1500px){
    .contact-container{
      max-width: 400px;
    }
    .contact-des1{
      margin: 0 auto;
      margin-top: 100px;
      font-size: 28px;
    }
    .contact-des2{
      font-size: 20px;
      line-height: 30px;
    }
    .contact-type a{
      position: relative;
      margin: 0 20px;
      width: 50px;
      height: 50px;
      border: 1px solid #FFF;
      border-radius: 50%;
    }
  }
</style>
